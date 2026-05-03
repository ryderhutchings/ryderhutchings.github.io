+++
title = "Contact"
menu = "main"
weight = 4
+++

<style>
  .contact-form {
    max-width: 32rem;
  }

  .contact-form label {
    display: block;
    margin-top: 1.2rem;
    margin-bottom: 0.3rem;
    font-weight: bold;
  }

  .contact-form input,
  .contact-form textarea {
    width: 100%;
    padding: 0.6rem 0.75rem;
    font-size: 1rem;
    font-family: inherit;
    border-radius: 4px;
    box-sizing: border-box;
    background-color: #fff;
    color: #000;
    border: 1px solid #ccc;
  }

  .contact-form textarea {
    resize: vertical;
  }

  .contact-form input::placeholder,
  .contact-form textarea::placeholder {
    color: #888;
  }

  .contact-form button {
    display: block;
    margin-top: 1.2rem;
    width: 100%;
    padding: 0.65rem;
    font-size: 1rem;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
    font-weight: bold;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    background-color: #000;
    color: #fff;
  }

  .contact-form button:hover {
    opacity: 0.8;
  }

  @media (prefers-color-scheme: dark) {
    .contact-form input,
    .contact-form textarea {
      background-color: #2a2a2a;
      color: #fff;
      border-color: #555;
    }
    .contact-form input::placeholder,
    .contact-form textarea::placeholder {
      color: #888;
    }
    .contact-form button {
      background-color: #fff;
      color: #000;
    }
  }
</style>

<form action="https://api.web3forms.com/submit" method="POST" class="contact-form">
  <input type="hidden" name="access_key" value="29dbcce8-b4ae-4e79-914b-c095ad09463d">
  <input type="hidden" name="form_name" value="ryderhutchings.com">
  <input type="hidden" name="redirect" value="">

  <label for="name">Name</label>
  <input type="text" id="name" name="name" placeholder="Your Name" required>

  <label for="email">Email</label>
  <input type="email" id="email" name="email" placeholder="you@example.com" required>

  <label for="message">Message</label>
  <textarea id="message" name="message" rows="5" placeholder="Your message here…" required></textarea>

  <button type="submit">Send Message</button>
</form>
<br>

---

#### OK:
- Questions about my projects.
- Content feedback slash advice.
- Collaboration/sponsorship inquiries.
- Bug reports or issues with my projects.
- Job or freelance opportunities.
- Just saying Hi.

#### Not OK:
- Spam.
- Unsolicited marketing.
- Hateful or inappropriate messages.
- Low-effort or spammy AI-generated messages.
- Sending files or links without prior outreach.
