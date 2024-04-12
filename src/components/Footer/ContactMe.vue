<template>
  <section id="contact-me">
    <h2>Get in touch!</h2>
    <p>Thank you so much for visiting my website. If you have a question or just want to say hi, feel free to email me
      and I'll get back to you
      when I can.</p>
    <a href="mailto:hello@martinshelley.com" class="button">Message me!</a>
    <!-- <p>
      Feel free to send over any questions you may have. I look forward to
      hearing from you!
    </p> -->
    <!-- <form>
      <div class="form-section" form-question="name">
        <label for="name">Full Name</label>
        <input type="text" name="name" id="name" required />
      </div>
      <div class="form-section" form-question="email">
        <label for="email">Email</label>
        <input type="email" name="email" id="email" required />
      </div>
      <div class="form-section" form-question="subject">
        <label for="subject">Subject</label>
        <input type="text" name="subject" id="subject" required />
      </div>
      <div class="form-section" form-question="message">
        <label for="message">Message</label>
        <textarea name="message" rows="5" id="message"></textarea>
      </div>
      <button type="submit" class="button">Submit</button>
    </form> -->
  </section>
</template>


<style lang="scss" scoped>
section {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 600px;

  h2 {
    margin-bottom: 20px;
  }

  p {
    margin-bottom: 30px;
  }

  h2,
  p {
    text-align: center;
  }

  .button {
    text-decoration: none;
    text-align: center;
  }

  .email {
    color: grey;
    text-decoration: none;

    &:hover {
      text-decoration: underline;
      color: #000;
    }
  }

  form {
    display: grid;
    grid-template-columns: 1fr 1fr;
    column-gap: 75px;

    // grid-template-rows: 1fr 1fr 0.5fr;
    .form-section {
      display: flex;
      flex-direction: column;
      gap: 10px;
      margin-bottom: 10px;

      input {
        // height: 25px;
        padding: 15px;
      }
    }

    .form-section[form-question="subject"],
    .form-section[form-question="message"] {
      grid-column: 1 / 3;
    }
  }
}

textarea {
  resize: vertical;
  height: 200px;
}

@media screen and (max-width: 768px) {
  section {
    form {
      grid-template-columns: 1fr;

      .form-section[form-question="subject"],
      .form-section[form-question="message"] {
        grid-column: unset;
      }

      button {
        width: 100%;
      }
    }
  }

  p {
    max-width: 300px;
  }
}
</style>