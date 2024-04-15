<template>
  <section id="contact-me">
    <h2>Get in touch!</h2>
    <p>Thank you so much for visiting my website. If you have a question or just want to say hi, feel free to email me
      and I'll get back to you
      when I can.</p>
    <a href="mailto:hello@martinshelley.com" class="button">Message me!</a>
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
}

textarea {
  resize: vertical;
  height: 200px;
}

@media screen and (max-width: 768px) {
  p {
    max-width: 300px;
  }
}
</style>