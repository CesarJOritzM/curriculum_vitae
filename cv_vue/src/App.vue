<template>
  <div id="app">
    <div id="Cv" class="contenido open"><Cv /></div>
    <div id="Abountme" class="contenido"><AboutMe /></div>
    <div id="Contacme" class="contenido"><ContactMe /></div>
    <div id="Briefcase" class="contenido"><Briefcase /></div>

    <footer>
      <ul class="menu">
        <div class="items">
          <li v-for="(item, index) in menu" :key="index" :id="item.name">
            <a href="#" :ref="item.name" :class="item.class"
              ><img
                :src="item.image"
                class="menu-item"
                @click="manejoClick($event)"
              />
            </a>
          </li>
        </div>
      </ul>
    </footer>
  </div>
</template>

<script>
import cv from "./assets/images/cv-white.png";
import aboutme from "./assets/images/about-me-white.png";
import contact from "./assets/images/contact-me-white.png";
import work from "./assets/images/briefcase-white.png";
import AboutMe from "./components/about-me.vue";
import ContactMe from "./components/contact-me.vue";
import Briefcase from "./components/briefcase.vue";
import Cv from "./components/cv.vue";

export default {
  name: "app",
  data: () => {
    return {
      menu: [
        { name: "cv", image: cv, class: "" },
        { name: "about-me", image: aboutme, class: "" },
        { name: "contact-me", image: contact, class: "" },
        { name: "work", image: work, class: "" },
      ],
    };
  },
  components: {
    AboutMe,
    ContactMe,
    Briefcase,
    Cv,
  },
  methods: {
    
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=B612:ital,wght@0,400;0,700;1,400;1,700&display=swap");
* {
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  color: #1c1e1f;
  background: #ffffff;
  overflow-x: hidden;
}
.contenido {
  width: 100%;
  height: 100%;
  display: none;
}
.open {
  display: block;
}
.title {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 2.5rem 0rem;
}
.title h1 {
  font-size: 1.5rem;
}
footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 3rem;
  z-index: 2000;
  background: #3198df;
}
.menu {
  list-style: none;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}
.items {
  display: flex;
  width: 17.2rem;
  justify-content: space-between;
}
.selected {
  border: 1px solid red;
  width: 2.5rem;
  height: 2.5rem;
}
.items li a {
  display: inline-block;
  width: 100%;
  height: 100%;
}
@media screen and (min-width: 720px) {
  .contenido {
    width: calc(100%-5.625rem);
    margin-left: 5.625rem;
    height: 100%;
  }
  .title {
    margin: 3.75rem 0rem;
  }
  .title h1 {
    font-size: 1.7rem;
  }
  footer {
    left: 0;
    width: 5.625rem;
    height: 100%;
  }
  .menu {
    flex-direction: column;
    justify-content: center;
  }
  .items {
    flex-direction: column;
    width: 100%;
    height: 20.6875rem;
    margin: 0px 0px;
    align-items: center;
    justify-content: initial;
  }
  .items li {
    margin: 0px 0px 50px 0px;
  }
  .menu-item {
    width: 2.5rem;
    height: 2.5rem;
  }
}
@media screen and (min-width: 1024px) {
  #contact-me {
    display: none;
  }
  .title h1 {
    font-size: 1.75rem;
  }
  .items {
    height: 15rem;
  }
}
</style>
