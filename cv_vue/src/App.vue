<template>
  <div id="app">

    <div id ='Cv' class='contenido' ><Cv/></div>
    <div id ='Abountme' class='contenido' > <AboutMe/></div>
    <div id ='Contacme' class='contenido open' ><ContactMe/></div>
    <div id ='Briefcase' class='contenido' ><Briefcase/></div>

    <footer>
      <ul class="menu">
        <div class="items">
          <li v-for='(item,index) in menu'
              :key='index'
              :title='item.name'
              :class="item.class"
            ><a href='#' 
                :ref='item.name' :id='item.name'
              ><img :src='item.image' class="menu-item" :id='item.name'
                 @click='manejoClick($event)'>
              </a>
          </li>
        </div>
      </ul>
    </footer>
  </div>
</template>

<script>
import cv from "./assets/images/cv-white.png"
import aboutme from "./assets/images/about-me-white.png"
import contact from "./assets/images/contact-me-white.png"
import work from "./assets/images/briefcase-white.png"
import AboutMe from "./components/about-me.vue"
import ContactMe from "./components/contact-me.vue"
import Briefcase from "./components/briefcase.vue"
import Cv from "./components/cv.vue"

export default {
  name: 'app',
  data: ()=>{
    return{
      menu: [{name:'cv',image:cv, class:""},
             {name:'about-me',image:aboutme, class:""},
             {name:'contact-me',image:contact, class:"selected"},
             {name:'work',image:work,class:""}]
    }
  },
  components: {
    AboutMe,
    ContactMe,
    Briefcase,
    Cv
  },
  methods: {
   manejoClick: (evento)=> {
      console.log(evento.target.id)
      this.cambiarSelected(evento.target.id)
      
    },
   cambiarSelected: (id)=> {
      for (var tab of this.$data.menu){
        if (tab.name === id){
          console.log(id);
        }
      }
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=B612:ital,wght@0,400;0,700;1,400;1,700&display=swap');
*{
  margin: 0;
  padding: 0;
}
body{
  width: 100vw;
  height: 100vh;
  font-family: 'B612', sans-serif;
  color: #1C1E1F;
  background: #ffffff;
  overflow-x: hidden;
}
.contenido{
  display: none;
}
.open{
  display: block;
}
@media screen and (min-width:320px){
    .title{
    width: 100%;
    height: 1.8125rem;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 2.5rem;
    margin-bottom: 2.5rem;
  }
  .title h1{
    height: 1.8125rem;
    font-size: 1.5rem;
  }
 footer{
   position: fixed;
   bottom: 0;
   width: 100%;
   height: 3rem;
   z-index:2000;
   background:#3198DF;
  }
  .menu{
    list-style: none;
  }
  .items{
    display: flex;
    flex-direction: row;
    width: 75%;
    margin: 0.3125rem 2.8125rem ;
    justify-content: space-between;
  }
  .selected{
    border: 1px solid red;
    width:2.5rem;
    height: 2.5rem;
  }
  .items li a{
    display: inline-block;
    width: 100%;
  }
}
@media screen and (min-width: 415px) {
  
}


</style>
