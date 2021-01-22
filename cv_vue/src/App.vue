<template>
  <div id="app">
    <header id="show" class="">
      <ul class="menu">
        <i class="fas fa-bars" @click="manejarClick($event)" ref="button"></i>
        <div class="items">
          <li
            v-for="(item, index) in menu"
            :key="index"
            :class="item.class"
            :id="item.name"
            @click="manejarClick($event)"
          >
            <img :src="item.image" :id="item.name" class="menu-item" />
            <p :id="item.name">{{ item.text }}</p>
          </li>
        </div>
      </ul>
    </header>
    <button
      v-show="showContact"
      class="boton"
      @click.stop="showPopup"
    >
      Contactame
    </button>
    <div v-show="showComplete" v-click-outside="hidePopup">
      <ContactMe />
    </div>
    <div id="Cv" class="contenido"><Cv /></div>
    <div id="About-me" class="contenido open"><AboutMe /></div>
    <div id="Contact-me" class="contenido"><ContactMe /></div>
    <div id="Briefcase" class="contenido"><Briefcase /></div>
  </div>
</template>

<script>
import Vue from "vue";
import cv from "./assets/images/cv-white.png";
import aboutme from "./assets/images/about-me-white.png";
import contact from "./assets/images/contact-me-white.png";
import work from "./assets/images/briefcase-white.png";
import AboutMe from "./components/about-me.vue";
import ContactMe from "./components/contact-me.vue";
import Briefcase from "./components/briefcase.vue";
import Cv from "./components/cv.vue";

function capitalize(word) {
  return word[0].toUpperCase() + word.slice(1);
}

export default {
  name: "app",
  data: () => {
    return {
      menu: [
        { name: "cv", image: cv, text: " Curriculum", class: "0" },
        {
          name: "about-me",
          image: aboutme,
          text: " Acerca de mi",
          class: "selected",
        },
        { name: "contact-me", image: contact, text: " Contactame", class: "0" },
        { name: "briefcase", image: work, text: " Portafolio", class: "0" },
      ],
      showCompleteMenu: false,
      showComplete: false,
      showContact: true,
      tabActive: null,
      menuItemActive: null,
    };
  },
  methods: {
    manejarClick(event) {
      if (event.target.className === "fas fa-bars") {
        this.showCompletemenu();
      } else {
        if (event.target.id === "cv") {
          this.showContact = false
          this.cambiarSelected(event.target.id);
        } else {
          this.showContact = true;
          this.cambiarSelected(event.target.id);
        }
      }
    },
    showCompletemenu() {
      if (!this.showCompleteMenu) {
        document.getElementById("show").className = "extend";
        this.showCompleteMenu = !this.showCompleteMenu;
      } else {
        document.getElementById("show").className = "";
        this.showCompleteMenu = !this.showCompleteMenu;
      }
    },
    cambiarSelected(id) {
      this.tabActive = document.getElementsByClassName("open");
      this.menuItemActive = document.getElementsByClassName("selected");
      for (var item of this.menu) {
        if (item.name === id) {
          if (capitalize(id) === this.tabActive[0].id) {
            console.log("son iguales");
          } else {
            document.getElementById(this.tabActive[0].id).className =
              "contenido";
            document.getElementById(this.menuItemActive[0].id).className = "0";
            document.getElementById(capitalize(id)).className =
              "contenido open";
            document.getElementById(id).className = "selected";
            this.tabActive = document.getElementsByClassName("open");
            this.menuItemActive = document.getElementsByClassName("selected");
          }
        }
      }
    },
     showPopup() {
      this.showComplete = true;
    },
    hidePopup() {
      this.showComplete = false;
    }
  },
  components: {
    AboutMe,
    ContactMe,
    Briefcase,
    Cv,
  },  
};
Vue.directive("click-outside",{
  bind: function (el, binding, vnode) {
      el.eventSetDrag = function () {
          el.setAttribute('data-dragging', 'yes');
      }
      el.eventClearDrag = function () {
          el.removeAttribute('data-dragging');
      }
      el.eventOnClick = function (event) {
          var dragging = el.getAttribute('data-dragging');
          // Check that the click was outside the el and its children, and wasn't a drag
          if (!(el == event.target || el.contains(event.target)) && !dragging) {
              // call method provided in attribute value
              vnode.context[binding.expression](event);
          }
      };
      document.addEventListener('touchstart', el.eventClearDrag);
      document.addEventListener('touchmove', el.eventSetDrag);
      document.addEventListener('click', el.eventOnClick);
      document.addEventListener('touchend', el.eventOnClick);
  }, unbind: function (el) {
      document.removeEventListener('touchstart', el.eventClearDrag);
      document.removeEventListener('touchmove', el.eventSetDrag);
      document.removeEventListener('click', el.eventOnClick);
      document.removeEventListener('touchend', el.eventOnClick);
      el.removeAttribute('data-dragging');
  },
});
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
  border-radius: 0rem 0rem 0.3125rem 0.3125rem;
}
.selected img {
  filter: brightness(1%);
}
.boton{
  display:none;
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
    font-size: 1.875rem;
    color: white;
    margin: 1.875rem 1.875rem;
    position: absolute;
    top: 0;
  }
  .menu {
    flex-direction: column;
  }
  .items {
    flex-direction: column;
    width: 15rem;
    height: 20.6875rem;
    justify-content: initial;
  }
  .items li {
    margin: 0rem 0rem 0rem 0.3125rem;
    padding: 1.25rem;
    width: 12.4375rem;
    height: 5rem;
    display: flex;
    align-items: center;
    text-align: left;
  }
  .items li p {
    color: white;
    font-size: 1.1875rem;
    font-weight: 300;
    display: block;
    margin-left: 1.5625rem;
  }
  .menu-item {
    width: 2.5rem;
    height: 2.5rem;
  }
  .selected {
    background: white;
    border-radius: 0.625rem;
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
  .boton {
    position: absolute;
    right: 0;
    width: 11.25rem;
    height: 3.125rem;
    margin: 0rem 6.375rem 0rem 0rem;
    font-size: 20px;
    font-weight: bold;
    background: #3198df;
    color: #ffffff;
    border-radius: 10px;
    border: #1c1e1f;
  }
}
</style>
