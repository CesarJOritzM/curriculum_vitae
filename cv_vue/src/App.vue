<template>
  <div id="app">
    <header>
      <div class="title">
        <h1>Sobre mi</h1>
      </div>
    </header>
    <section class="hero">
      <img src="./assets/images/photo.svg" alt="">
      <h2>Cesar Javier Ortiz Montero</h2>
      <p>Desarrollador web Front-end</p>
      <ul id="social-container">
          <li v-for='(red,index) in social'
              :key='index'
              :title='red.name'
              ><img :id='red.name' :src='red.image' class="social-item">
          </li>
      </ul>
    </section>
     <ul class="menu">
       <div id="items">
        <li v-for='(item,index) in menu'
            :key='index'
            :title='item.name'
            clas>
            <a href='#'
              :ref='item.name'
              :id='item.name'
                ><img :src='item.image' class="menu-item">
            </a>
        </li>
       </div>
    </ul>
  </div>
</template>

<script>
import cv from "./assets/images/cv.svg"
import aboutme from "./assets/images/about-me.svg"
import contact from "./assets/images/contact-me.svg"
import briefcase from "./assets/images/briefcase.svg"
import git from "./assets/images/git.svg"
import linkedin from "./assets/images/in.svg"
import ig from "./assets/images/ig.svg"

export default {
  name: 'app',
  data: function (){
    return {
      
      menu: [{name:'cv',image:cv},
             {name:'about-me',image:aboutme},
             {name:'contact-me',image:contact},
             {name:'briefcase',image:briefcase}],
             
      social: [{name:'git',image:git},
             {name:'in',image:linkedin},
             {name:'ig',image:ig}]
    }
  },
  components: {
  },
  methods: {
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
  font-family: 'B612', sans-serif;
}

@media (max-width: 360px){
  
  .menu{
    width: 100%;
    height: 3rem;
    background: #3198DF;
    position: fixed;
  }
  #items{
    margin: 0px 45px;
    display: flex;
    justify-content: space-between;
  }
  .menu li{
    list-style: none;
    background: #ffffff;
    width: 2.5rem;
    height: 2.5rem;
    align-content: center;
  }
  .menu li a {
    text-decoration: none;
    width:1.875rem;
    height:1.875rem;
  }
  .menu-item{
    width:1.875rem;
    height:1.875rem;  
  }
}
</style>
