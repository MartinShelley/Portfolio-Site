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
          Following University, I ventured into IT Support then moved onto different roles within the Analytics
          industry, including a role where I led on projects (including developing A/B tests) for big clients such as
          Ticketmaster & Carphone Warehouse. When the pandemic struck, I rediscovered my passion for web development and
          embarked on a career transition.
        </p>
        <p>
          Leveraging my background in CRO and A/B testing, I secured a role as a Front End Developer at The White
          Company. Here, I delved into many projects, but wanted to continue to grow further as a developer and work
          with different technologies, mainly front end frameworks.
        </p>
        <p>
          Now, at I-Neda, I'm continuing my learning journey as a developer using Angular & Typescript while learning
          Node.js in my spare time. I'm eager to further my skills and tackle exciting new projects on the horizon.
        </p>
        <a href="./cv.pdf" target="_blank">
          <button class="button">Download my public CV</button>
        </a>
      </div>
      <img src="../../assets/me-300.jpg" />
    </div>
  </section>
</template>

<style lang="scss" scoped>
#about-me {
  margin: 150px 0;
  // padding: 75px 0;

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