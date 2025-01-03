<template>
  <section id="about-me">
    <h2 id="about-me-heading">About Me</h2>
    <div class="about-me-body">
      <div class="copy">
        <p>
          Ever since I was young, I've always been fascinated by technology. At a young age I remember asking my dad if
          I could help setup the new family computer. From there, my passion for technology grew from taking apart many
          laptops in my teens to building a simple website so that my school friends could play games at the start of
          school (if any of my old school teachers read this.. I'm sorry!).
        </p>
        <p>
          Following University, I began my career in IT Support before transitioning into different roles within the Analytics
          industry, where I gained valuable experience leading projects and developing A/B tests for high-profile clients such as
          Ticketmaster & Carphone Warehouse. When the pandemic hit, I rediscovered my passion for web development and committed to a career transition.
        </p>
        <p>
          Leveraging my experience in A/B testing & my growing technical skillset, I secured a role as a Front End Developer at The White
          Company. There, I delved into many high impacting projects including the implementation of a 'sticky' add to bag button which resulted in a £1.8M annual incremental revenue benefit. However, driven by my eagerness to learn and grow, I sought opportunities to deepen my technical expertise and expand my toolkit.
        </p>
        <p>
          Now, as a Front End Developer at I-Neda, I'm continuing my journey as a developer specialising in Angular & Typescript while actively learning
          Node.js & React in my spare time. I'm eager to further my skills even more, embrace new challenges and tackle exciting new innovative projects on the horizon.
        </p>
        <a href="./CV.pdf" target="_blank">
          <button class="button">Download my public CV</button>
        </a>
      </div>
      <img src="../../assets/me-300.jpg" alt="Image of me"/>
    </div>
  </section>
</template>

<style lang="scss" scoped>
#about-me {
  margin: 150px 0;

  h2 {
    text-align: center;
  }

  .about-me-body {
    display: flex;
    justify-content: space-between;
    gap: 50px;

    .copy {
      width: 70%;

      p {
        margin: 0 0 15px;

        &:last-of-type {
          margin-bottom: 30px;
        }
      }

      button {
        width: 250px;
      }
    }

    img {
      height: 100%;
      border-radius: 25px;
    }
  }
}

@media screen and (max-width: 1000px) {
  #about-me {
    margin: 25px 0;

    .about-me-body {
      flex-direction: column-reverse;

      .copy {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: unset;
      }

      img {
        width: 250px;
        height: auto;
        margin: 0 auto;
        border-radius: 15px;
      }
    }
  }
}
</style>