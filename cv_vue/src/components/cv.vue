<template>
  <div id="cv">
  </div>
</template>

<script>
// import certificate from "../assets/images/certificate.png"
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
      tools:[{name:"vue",img:vue,link:""},
             {name:"react",img:react,link:""},
             {name:"bootstrap",img:bootstrap,link:""},
             {name:"sails",img:sails,link:""},
             {name:"node",img:node,link:""},
             {name:"js",img:js,link:""},
             {name:"css",img:css,link:""},
             {name:"html",img:html,link:""}],  
             
      titles:[{title:"Fundamentos de python",descripcion:"Orientado en el desarrollo de las bases de la programación de computadores y resolución de problemas básicos utilizando el lenguaje de programación Python. "},
              {title:"Git para proyectos",descripcion:"Abarca la identificación de las principales ventajas tales como: trabajo en equipo, mayor autonomía. estructura en árbol, sistema escalable."},
              {title:"Web Fron-end",descripcion:"Uso de las tecnologias HTML, CSS, JavaScript y Bootstrap, que busca desarrollar habilidades y destrezas del desarrollo de sitios Web, que incluyen interfaces usables, atractivas, adaptativas (responsive) en cualquier tipo de dispositivo."},
              {title:"Web Back-end",descripcion:"Enfocado en Node ya que se aprovecha el conocimiento en JavaScript para convertirse en un ambiente de programación que adapta el lenguaje, nacido para entornos Front End, en un lenguaje de uso general que puede emplearse en ambientes Back End. También exploramos el framework Sails que permite facilitar la generación de aplicaciones Web más complejas, proporcionando una estructura para la inserción de piezas de código que componen una aplicación Web para su posterior ejecución."},
              {title:"Framework Javascript",descripcion:"Se identifican los conceptos fundamentales de JavaScript. Especialmente, los conceptos necesarios para desarrollar aplicaciones Web que consuman APIs, intercambien información en formato JSON y manejen comunicación asíncrona. También se exploran dos de los frameworks más utilizados de JavaScript: React y Vue para la creación de soluciones Front End robustas usando JavaScript como lenguaje interpretado base."},
              {title:"Bases de datos",descripcion:"Manejo de bases de datos SQL y NoSQL usando herramientas como MySql, PostgreSQL, MongoDB y CauchDB"}],
    }
  },
  props: {
  }
}
</script>

<style scoped>
@media screen and (min-width:320px){

}
</style>