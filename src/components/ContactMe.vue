<template>
  <section id="contact-me">
    <h3>Get in touch!</h3>
    <form>
      <label for="name">Name</label>
      <input type="text" name="name" id="name" required />
      <label for="email">Email</label>
      <input type="email" name="email" id="email" required />
      <label for="message">Message</label>
      <textarea name="message" rows="5" id="message"></textarea>
      <button type="submit">Submit</button>
    </form>
  </section>
</template>


<style lang="scss" scoped>
textarea {
  resize: vertical;
}
</style>