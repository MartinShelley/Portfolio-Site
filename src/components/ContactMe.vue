<template>
  <section id="contact-me">
    <h2>Get in touch!</h2>
    <form>
      <div class="form-section">
        <label for="name">Name</label>
        <input
          type="text"
          name="name"
          id="name"
          placeholder="Enter your name"
          required
        />
      </div>
      <div class="form-section">
        <label for="email">Email</label>
        <input
          type="email"
          name="email"
          id="email"
          placeholder="Enter your email address"
          required
        />
      </div>
      <div class="form-section message">
        <label for="message">Message</label>
        <textarea
          name="message"
          rows="5"
          id="message"
          placeholder="Enter your message"
        ></textarea>
      </div>
      <button type="submit">Submit</button>
    </form>
  </section>
</template>


<style lang="scss" scoped>
section {
  background-color: #f4f4f4;
  color: #1a1b1f;
  padding: 20px 100px;

  form {
    display: grid;
    grid-template-columns: 1fr 1fr;
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

    .message {
      grid-column: 1 / 3;
    }
  }
}
textarea {
  resize: vertical;
  height: 200px;
}
</style>