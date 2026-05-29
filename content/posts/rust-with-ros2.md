+++
title = "Rust with ROS2: What Are the Odds?"
date = 2026-05-28
description = "Evaluating the current state, benefits, and challenges of using Rust in the ROS2 ecosystem."
[taxonomies]
tags = ["rust", "ros2", "robotics", "systems-engineering"]
+++

The standard playbook for building robotics stacks is well-known: fast, mission-critical nodes go into C++, and the rest of the prototyping gets duct-taped together with Python. 

This has been the default reality in ROS2. But debugging a C++ segmentation fault on a companion computer mid-flight is a massive liability. As robotics pushes into domains where failure simply isn't an option—like defense tech, heavy UAVs, or tight embedded systems—the tolerance for silent memory leaks or race conditions drops to zero.

Naturally, the industry is looking at Rust. But what is the actual reality of dropping Rust into a ROS2 stack today? Is it just hype, or is it production-ready?

### The `rclrs` Situation

ROS2 has a C layer at its foundation (`rcl`). `rclcpp` (C++) and `rclpy` (Python) simply wrap around it. The Rust answer to this architecture is **`rclrs`**.

A couple of years ago, `rclrs` was basically a neat weekend project for enthusiasts. Today, it is getting serious industry backing. It is entirely possible to write core nodes, publishers, subscribers, and services in pure Rust.

### The Case for Rust

* **No More Data Races:** Robotics is massively concurrent by default. Systems are constantly reading IMU data, calculating kinematics, and firing actuators at the exact same time. Managing that in C++ leaves systems vulnerable to pointer errors and crashes. Rust's borrow checker enforces thread safety at compile time, eliminating data races before the code ever compiles. 
* **Hardware Control meets Cargo:** Developers get the bare-metal control absolutely needed for hardware like STM32s or custom mission computers, while utilizing `cargo` instead of fighting with `CMake` for hours just to add a single dependency.
* **The Accountability Gap:** Using AI tools to code faster is the new normal, but deploying fully AI-generated C++ into a mission-critical flight controller is a massive accountability risk. Strict, compiler-enforced safety guarantees are mandatory. Rust provides that foundational trust.

### The Rough Edges

There is no point in sugarcoating it. Dropping Rust into an existing ROS2 workspace is not completely frictionless yet.

* **The Legacy C++ Wall:** The entire ecosystem is built on C++. Leveraging the Nav2 stack or existing hardware drivers requires writing bindings. Tools like `cxx` help significantly, but wrapping massive C++ libraries is still a chore.
* **Missing Features:** `rclrs` does not have 100% parity with `rclcpp` just yet. If a project relies on highly specific lifecycle node patterns, workarounds might be necessary.
* **Mental Overhead:** Getting a PX4 SITL and Gazebo environment running smoothly is hard enough (especially when wrangling Podman containers and custom Linux setups). Introducing the Rust learning curve to a C++ focused codebase will naturally slow down initial velocity.

### The Verdict

So, what are the odds?

If the plan is to rewrite an entire legacy C++ robotics stack in Rust by next month... zero. The ecosystem is not ready for a sudden, total rewrite.

However, for building a *new* subsystem—like a telemetry ingestion backend, a safety monitor, or a high-throughput C2 link—Rust is rapidly becoming the best tool for the job.

The immediate future of ROS2 is hybrid. Keep the legacy hardware drivers in C++, keep the data scripts in Python, but shift the high-stakes, concurrent backend nodes to Rust.