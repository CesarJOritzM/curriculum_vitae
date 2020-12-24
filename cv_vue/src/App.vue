<template>
  <div id="app">
    <div id="contacto">
      <button> Contactame <i class="fas fa-angle-down"></i></button>
    </div>
    <div class="content">
      <div class="content_title">
        <h1>Cesar Javier Ortiz Montero</h1>
      </div>
      <div class="content_body">
        <div id="foto">
          <img src="./assets/Imagenes/obrero.svg" alt="">
        </div>  
        <div id="botones">
          <button class="boton" id="cv">
            <img src="./assets/Imagenes/curriculum-vitae.svg" alt="Curriculum">
          </button>
          <button class="boton" id="portafolio">
            <img src="./assets/Imagenes/portafolio.svg" alt="portafolio">
          </button>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
// import contacto from './components/Contacto.vue'

export default {
  name: 'App',
  data: function() {
    return{

    }
  },
  components: {
    // contacto
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
#root {
  width: 100%;
  height: 100%;
  position: relative;
  overflow-x: hidden;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  background: #F1F6F9;
}
#contacto button{
  width: 8.3125rem;
  height: 2.5rem;
  border-radius: 0.6rem;
  background: #394867;
  color: #F1F6F9;
  font-size: 1rem;
  padding: 0.625rem;
  border: solid black 1px;
  cursor: pointer;
}
#contacto i{
  color: #9BA4B4;
  padding-left: 0.3125rem;
}
.content_title h1{
  width: 266px;
  height: 26px;
  font-size: 1.3rem;
  font-weight: bold;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
.content_body #foto img{
  width: 12.5rem;
  height: 12.5rem;
}
.content_body #botones{
  width: 20rem;
  height: 4.375rem;
  left: 1.25rem;
  top: 25.375rem;
}
.content_body .boton{
  width: 5.625ren;
  height: 4.375rem;
  background: #394867;
  border: none;
  border-radius: 0.625rem;
  border: solid black 1px;
  cursor: pointer;
}
.content_body #botones .boton img{
  width: 3.125rem;
  padding: 0.625rem 1.25rem;
}
@media (max-width: 360px){
  
}
</style>
