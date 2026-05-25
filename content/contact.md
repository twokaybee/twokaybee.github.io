+++
title = "Contact"
description = "Get in touch"
date = 2026-05-25
template = "page.html"
+++

Drop me a message and I will get back to you as soon as possible.

<form id="contact-form" action="https://formspree.io/f/mzdwayvn" method="POST" style="margin-top: 2rem;">
  <div style="margin-bottom: 1rem;">
    <label for="name" style="display: block; margin-bottom: 0.5rem;">Name</label>
    <input type="text" id="name" name="name" required style="width: 100%; padding: 0.5rem; background: transparent; border: 1px solid #ccc; color: inherit;">
  </div>
  
  <div style="margin-bottom: 1rem;">
    <label for="email" style="display: block; margin-bottom: 0.5rem;">Email</label>
    <input type="email" id="email" name="email" required style="width: 100%; padding: 0.5rem; background: transparent; border: 1px solid #ccc; color: inherit;">
  </div>
  
  <div style="margin-bottom: 1rem;">
    <label for="message" style="display: block; margin-bottom: 0.5rem;">Message</label>
    <textarea id="message" name="message" rows="5" required style="width: 100%; padding: 0.5rem; background: transparent; border: 1px solid #ccc; color: inherit;"></textarea>
  </div>
  
  <button type="submit" id="contact-button" style="padding: 0.5rem 1rem; cursor: pointer; background: #fff; color: #000; border: none; font-weight: bold;">Send Message</button>
  <p id="contact-status" style="margin-top: 1rem; font-weight: bold;"></p>
</form>

<script>
  var form = document.getElementById("contact-form");
  var statusMessage = document.getElementById("contact-status");

  async function handleSubmit(event) {
    event.preventDefault();
    var data = new FormData(event.target);
    
    fetch(event.target.action, {
      method: form.method,
      body: data,
      headers: {
          'Accept': 'application/json'
      }
    }).then(response => {
      if (response.ok) {
        statusMessage.innerHTML = "Message sent successfully! I will get back to you soon.";
        statusMessage.style.color = "#4ade80"; // A subtle green success message
        form.reset(); // Clears the form inputs immediately
      } else {
        statusMessage.innerHTML = "Oops! There was a problem submitting your form.";
        statusMessage.style.color = "#f87171"; // A subtle red error message
      }
    }).catch(error => {
      statusMessage.innerHTML = "Oops! There was a problem submitting your form.";
      statusMessage.style.color = "#f87171";
    });
  }
  form.addEventListener("submit", handleSubmit);
</script>