<template>
  <div id="cv">
    <div class="title">
      <h1>Cirruculum Vitae</h1>
    </div>
    <div class="profile">
      <div class="pofile-title">
       <h2>Perfil profesional</h2>
      </div>
      <div class="profile-content">
        <p>Todo maestro tiene un principio, y con disciplina y dedicación se logra muchas cosas. Durante este tiempo de aprendizaje he estado manejando herramientas Front-End como HTML, CSS y JavaScript, además de frameworks como React, Vue y herramientas Bakc-end Node.js con librerías de express además de Sails y el MVC (Modelo, Vista, controlador). acostumbrado a cumplir con estrictos plazos de entrega además apasionado por el trabajo en equipo aportando soluciones creativas y prácticas.</p>
      </div>
    </div>
    <div class="studies">
      <h2>Estidios</h2>
      <div class="certificate" v-for='(item,index) in titles'
      :key ='index'
      :id='item.title'
      ><div class="certificate-title">
          <h3>{{item.title}}</h3>
          <a :href='item.link'><img src="../assets/images/certificate.png" alt="certificare"></a>
        </div>
        <div class="certificate-content">
          <div class="certificate-descripcion">
            <p>{{item.descripcion}}</p>
          </div>
        </div>
      </div>  
    </div>
  </div>
</template>

<script>
import vue from "../assets/images/vue-js.svg"
import react from "../assets/images/react.svg"
import bootstrap from "../assets/images/bootstrap.svg"
import sails from "../assets/images/sails.svg"
import node from "../assets/images/nodejs.svg"
import js from "../assets/images/javascript.svg"
import css from "../assets/images/css.svg"
import html from "../assets/images/html.svg"
// import email from "../assets/images/email-white.png"
// import phone from "../assets/images/phone-withe.png"
// import marker from "../assets/images/marker-white.png"

export default {
  name: 'Cv',
  data: function (){
    return {
      tools:[{name:"vue",img:vue},
             {name:"react",img:react},
             {name:"bootstrap",img:bootstrap},
             {name:"sails",img:sails},
             {name:"node",img:node},
             {name:"js",img:js},
             {name:"css",img:css},
             {name:"html",img:html}],  
             
      titles:[{title:"Fundamentos de python",link:"",descripcion:"Orientado en el desarrollo de las bases de la programación de computadores y resolución de problemas básicos utilizando el lenguaje de programación Python. "},
              {title:"Git para proyectos",link:"",descripcion:"Abarca la identificación de las principales ventajas tales como: trabajo en equipo, mayor autonomía. estructura en árbol, sistema escalable."},
              {title:"Web Fron-end",link:"",descripcion:"Uso de las tecnologias HTML, CSS, JavaScript y Bootstrap, que busca desarrollar habilidades y destrezas del desarrollo de sitios Web, que incluyen interfaces usables, atractivas, adaptativas (responsive) en cualquier tipo de dispositivo."},
              {title:"Web Back-end",link:"",descripcion:"Enfocado en Node ya que se aprovecha el conocimiento en JavaScript para convertirse en un ambiente de programación que adapta el lenguaje, nacido para entornos Front End, en un lenguaje de uso general que puede emplearse en ambientes Back End. También exploramos el framework Sails que permite facilitar la generación de aplicaciones Web más complejas, proporcionando una estructura para la inserción de piezas de código que componen una aplicación Web para su posterior ejecución."},
              {title:"Framework Javascript",link:"",descripcion:"Se identifican los conceptos fundamentales de JavaScript. Especialmente, los conceptos necesarios para desarrollar aplicaciones Web que consuman APIs, intercambien información en formato JSON y manejen comunicación asíncrona. También se exploran dos de los frameworks más utilizados de JavaScript: React y Vue para la creación de soluciones Front End robustas usando JavaScript como lenguaje interpretado base."},
              {title:"Bases de datos",link:"",descripcion:"Manejo de bases de datos SQL y NoSQL usando herramientas como MySql, PostgreSQL, MongoDB y CauchDB"}],
    }
  },
  props: {
  }
}
</script>

<style scoped>
@media screen and (min-width:320px){
  .profile{
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }
  .pofile-title{
    align-self: end;
    margin-left: 7.8%;
   }
  .profile-content{
    border-top: solid 1px #1C1E1F;
    width: 92%;
    background: #98CBEF;
    border-radius: 0px 0px 0px 1.25rem;
  }
  .profile-content p {
    text-align: justify;
    padding: 1.25rem 1.8125rem 1.25rem 1.25rem;
  }
  .studies{
    margin-top: 1.25rem;
    text-align: -webkit-right;
    
  }
  .studies h2{
    margin-left: 7.8%;
    margin-bottom: .625rem;
    text-align: left;
  }
 .certificate{
   width: 89.5%;
   margin-bottom:1.25rem ;
 }
 .certificate-title{
   display: flex;
   height: 1.5rem;
 }
 .certificate-content{
   text-align: justify;
   background: #98CBEF;
   border-radius: 0px 0px 0px 1.25rem;
   padding: 1.25rem 1.8125rem 1.25rem 1.25rem;
   border-top: solid 1px #1C1E1F;
 }
 #Bases de datos{
   height: 1.4375rem
 }
}
</style>