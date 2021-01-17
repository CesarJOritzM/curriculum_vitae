<template>
  <div id="app">
    <header id="show" class="">
      <ul class="menu">
        <i class="fas fa-bars" @click="showCompletemenu($event)"></i>
        <div class="items">
          <li
            v-for="(item, index) in icons"
            :key="index"
            :class="item.class"
            :id="item.name"
            @click="cambiarSelected($event)"
          >
            <img :src="item.image" :id="item.name" class="menu-item" />
            <p :id="item.name">{{ item.text }}</p>
          </li>
        </div>
      </ul>
    </header>

    <div id="Cv" class="contenido"><Cv /></div>
    <div id="About-me" class="contenido open"><AboutMe /></div>
    <div id="Contact-me" class="contenido"><ContactMe /></div>
    <div id="Briefcase" class="contenido"><Briefcase /></div>
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

var showComplete = false;
const menu = [
  { name: "cv", image: cv, text: " Curriculum", class: "0" },
  {
    name: "about-me",
    image: aboutme,
    text: " Acerca de mi",
    class: "selected",
  },
  { name: "contact-me", image: contact, text: " Contactame", class: "0" },
  { name: "briefcase", image: work, text: " Portafolio", class: "0" },
];
var tabActive = document.getElementsByClassName("open");
var menuItemActive = document.getElementsByClassName("selected");

function capitalize(word) {
  return word[0].toUpperCase() + word.slice(1);
}

export default {
  name: "app",
  data: () => {
    return {
      icons: menu,
    };
  },
  methods: {
    showCompletemenu: (event) => {
      if (event.target.className === "fas fa-bars") {
        if (!showComplete) {
          document.getElementById("show").className = "extend";
          showComplete = !showComplete;
        } else {
          document.getElementById("show").className = "";
          showComplete = !showComplete;
        }
      }
    },
    cambiarSelected: (event) => {
      for (var item of menu) {
        if (item.name === event.target.id) {
          if (capitalize(event.target.id) === tabActive[0].id) {
            console.log("son iguales");
          } else {
            document.getElementById(tabActive[0].id).className = "contenido";
            document.getElementById(menuItemActive[0].id).className = "0";
            document.getElementById(capitalize(event.target.id)).className =
              "contenido open";
            document.getElementById(event.target.id).className = "selected";
            tabActive = document.getElementsByClassName("open");
            menuItemActive = document.getElementsByClassName("selected");
          }
        }
      }
    },
  },
  components: {
    AboutMe,
    ContactMe,
    Briefcase,
    Cv,
  },
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
header {
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 3rem;
  z-index: 2000;
  background: #3198df;
}
.fas {
  display: none;
  cursor: pointer;
}
.menu {
  list-style: none;
  display: flex;
  height: 100%;
  justify-content: center;
}
.menu-item {
  margin-top: 0.3125rem;
  height: 1.875rem;
  width: 1.875rem;
}
.items {
  display: flex;
}
.items li {
  width: 3rem;
  height: 2.5rem;
  text-align: center;
  margin: 0px 1.25rem;
  cursor: pointer;
}
.items li p {
  display: none;
}
.selected {
  background: white;
  border-radius: 0px 0px 5px 5px;
}
.selected img {
  filter: brightness(1%);
}
@media screen and (min-width: 720px) {
  .contenido {
    width: calc(100% - 90px);
    margin-left: 5.625rem;
    height: 100%;
  }
  .title {
    margin: 3.75rem 0rem;
  }
  .title h1 {
    font-size: 1.7rem;
  }
  header {
    left: 0;
    width: 5.625rem;
    height: 100%;
    overflow: hidden;
    display: flex;
  }
  .fas {
    display: block;
    font-size: 30px;
    color: white;
    margin: 30px 30px;
    position: absolute;
    top: 0;
  }
  .menu {
    flex-direction: column;
  }
  .items {
    flex-direction: column;
    width: 240px;
    height: 20.6875rem;
    justify-content: initial;
  }
  .items li {
    margin: 0px 0px 0px 5px;
    padding: 20px;
    width: 199px;
    height: 80px;
    display: flex;
    align-items: center;
    text-align: left;
  }
  .items li p {
    color: white;
    font-size: 19px;
    font-weight: 300;
    display: block;
    margin-left: 25px;
  }
  .menu-item {
    width: 2.5rem;
    height: 2.5rem;
  }
  .selected {
    background: white;
    border-radius: 10px;
  }
  .selected p {
    filter: brightness(1%);
  }
  .extend {
    width: 250px;
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
