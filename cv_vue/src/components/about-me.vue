<template>
  <div id="acerca-de-mi">
    <div class="title">
      <h1>Sobre mi</h1>
    </div>
    <section class="hero">
      <img
        src="../assets/images/photo.svg"
        alt="foto de perfil"
        class="hero-photo"
      />
      <div class="name">
        <h2>Cesar Javier Ortiz Montero</h2>
        <p>Desarrollador web Front-end</p>
      </div>
      <ul class="social-container">
        <li v-for="(red, index) in social" :key="index" :title="red.name">
          <a target="_blank" :href="red.url"
            ><img :id="red.name" :src="red.image" class="social-item"
          /></a>
        </li>
      </ul>
      <div class="about-me-text">
        <p>
          Siempre me han gustado los retos, porque de esa forma puedes poner a
          prueba tu conocimiento, y eso es lo que he encontrado en el desarrollo
          web, todos los días te encuentras ante diferentes retos que requieren
          lo mejor de ti para encontrar la mejor solución, logrando así afianzar
          y expandir los límites de mis conocimientos, por ese motivó estoy a la
          búsqueda de experiencias saquen lo mejor de mí, a su vez rodearme de
          personas experimentadas para aprender de ellas y ser mejor cada día.
        </p>
      </div>
    </section>
  </div>
</template>

<script>
import git from "../assets/images/git.svg";
import linkedin from "../assets/images/in.svg";
import ig from "../assets/images/ig.svg";

export default {
  name: "AboutMe",
  data: function () {
    return {
      social: [
        { name: "git", image: git, url: "https://github.com/CesarJOritzM" },
        {
          name: "in",
          image: linkedin,
          url:
            "https://www.linkedin.com/in/cesar-javier-ortiz-montero-66955a186/?locale=es_ES",
        },
        { name: "ig", image: ig, url: "https://www.instagram.com/csar_otz/" },
      ],
    };
  },
  props: {},
};
</script>

<style scoped>
.hero {
  width: 100%;
  margin-top: 2.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.hero-photo {
  width: 15.625rem;
  height: 15.625rem;
}
.name {
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.name h2 {
  font-size: 1rem;
}
.name p {
  font-size: 1rem;
}
.social-container {
  list-style: none;
  display: flex;
  justify-content: center;
  width: 100%;
  margin-top: 0.525rem;
  margin-bottom: 1rem;
}
.social-item {
  width: 1.875rem;
  padding: 0 0.625rem 0 0;
}
.about-me-text {
  background: #98cbef;
  padding: 1.25rem 1.875rem;
  margin-bottom: 5rem;
  filter: drop-shadow(0px 4px 4px #4c6577);
}
.about-me-text p {
  text-align: justify;
}
@media screen and (min-width: 720px) {
  .hero-photo {
    width: 18.75rem;
    height: 18.75rem;
    margin-bottom: 3.74rem;
  }
  .name h2 {
    font-size: 1.375rem;
  }
  .name p {
    font-size: 1.2rem;
  }
  .social-item {
    width: 2rem;
  }
  .about-me-text {
    width: 75%;
    border-radius: 1.25rem;
    filter: drop-shadow(0px 4px 4px #4c6577);
  }
  .about-me-text p {
    text-align: center;
    font-size: 1.2rem;
  }
}
</style>
