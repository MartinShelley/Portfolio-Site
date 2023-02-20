<template>
  <section id="about-me">
    <h2 id="about-me-heading">About Me</h2>
    <div class="about-me-body">
      <div class="copy">
        <p>
          Ever since I was young, I've always been facinated by technology. At a
          young age I remember asking my dad if I could help setup the new
          family computer. From there, my passion for technology grew from
          taking apart many laptops in my teens to building a simple website so
          that my school friends could play games at the start of school (if any
          of my old school teachers read this.. I'm sorry!).
        </p>
        <p>
          Following University and the early years of my career, I've rekindled
          my love for technology and creating things on the web. More noteably
          in recent years I have led on CRO projects for some big named brands
          such as Carphone Warehouse, RBI (RELX group - previous owners of New
          Scientist Magazine & Farmers Weekly) & The White Company.
        </p>
        <p>
          Now, I'm looking for my next challenge as a Front-End Developer where
          I can continue to learn and grow.
        </p>
        <button>Download my public CV</button>
      </div>
      <img src="../../assets/DSC01128.jpg" />
    </div>
  </section>
</template>

<style lang="scss" scoped>
#about-me {
  // padding: 75px 0;
  h2 {
    text-align: center;
  }
  .about-me-body {
    display: flex;
    justify-content: center;
    gap: 50px;
    .copy {
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
      width: 60%;

      p {
        margin: 0;
      }

      button {
        width: 250px;
      }
    }
    img {
      max-width: 300px;
    }
  }
}
</style>