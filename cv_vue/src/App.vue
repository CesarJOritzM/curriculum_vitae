<template>
  <div id="app">

    <div id ='Cv' class='contenido ' ><Cv/></div>
    <div id ='Abountme' class='contenido ' > <AboutMe/></div>
    <div id ='Contacme' class='contenido open' ><ContactMe/></div>
    <div id ='Briefcase' class='contenido ' ><Briefcase/></div>

    <footer>
      <ul class="menu">
        <div class="items">
          <li v-for='(item,index) in menu'
              :key='index'
              :title='item.name'
            ><a href='#' 
                :ref='item.name' :id='item.name' :class='item.class'
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
             {name:'contact-me',image:contact, class:""},
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
#app{
  width: 100%;
  height: 100%;
}
.contenido{
  display: none;
}
.open{
  display: block;
}
@media screen and (min-width:360px){
    .title{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 2.5rem 0rem;
  }
  .title h1{
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
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
  .items{
    display: flex;
    width: 17.2rem;
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
    height: 100%;
  }
}
@media screen and (min-width: 720px){
  .contenido{
    width: 88.15%;
    margin-left: 11.85%;
    height: 100%;
  }

  .title{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 3.75rem 0rem;
  }
   .title h1{
    font-size: 1.7rem;
  }
  footer{
   position: fixed;
   left: 0;
   width: 11.85%;
   height: 100%;
   z-index:2000;
   background:#3198DF;
  }
  .menu{
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .items{
    display: flex;
    flex-direction:column;
    width: 100%; 
    height: 20.6875rem;
    margin: 0px 0px;
    align-items: center;
    justify-content: initial;
  }
  .items li{
    margin: 0px 0px 50px 0px;
  }
  .menu-item  {
    width: 2.5rem;
    height: 2.5rem;
  }
}


</style>
