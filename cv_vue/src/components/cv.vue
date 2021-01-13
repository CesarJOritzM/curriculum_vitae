<template>
  <div id="cv">
    <div class="title">
      <h1>Cirruculum Vitae</h1>
    </div>
    <div class="my-information">
      <figure class="photo">
        <img src="../assets/images/photo.svg" alt="foto de perfil" />
      </figure>
      <div class="information">
        <div
          class="contact"
          v-for="(item, index) in contact"
          :key="index"
          :id="item.cardname"
        >
          <img :src="item.img" :alt="item.cardname" />
          <div>
            <p>
              <strong>{{ item.cardname }}</strong>
            </p>
            <p>{{ item.name }}</p>
          </div>
        </div>
        <div class="lang">
          <p><strong>Español:</strong>Nativo</p>
          <p><strong>Ingles:</strong>Basico</p>
        </div>
        <div class="skills">
          <h3>habilidades de sofware</h3>
          <div
            class="sofware"
            v-for="(item, index) in tools"
            :key="index"
            :id="item.name"
          >
            <img :src="item.img" :alt="item.name" />
          </div>
        </div>
      </div>
    </div>
    <div class="my-studies">
      <div class="profile">
        <div class="pofile-title">
          <h2>Perfil profesional</h2>
        </div>
        <div class="profile-content">
          <p>
            Todo maestro tiene un principio, y con disciplina y dedicación se
            logra muchas cosas. Durante este tiempo de aprendizaje he estado
            manejando herramientas Front-End como HTML, CSS y JavaScript, además
            de frameworks como React, Vue y herramientas Bakc-end Node.js con
            librerías de express además de Sails y el MVC (Modelo, Vista,
            controlador). acostumbrado a cumplir con estrictos plazos de entrega
            además apasionado por el trabajo en equipo aportando soluciones
            creativas y prácticas.
          </p>
        </div>
      </div>
      <div class="studies">
        <h2>Estidios</h2>
        <div
          class="certificate"
          v-for="(item, index) in titles"
          :key="index"
          :id="item.id"
        >
          <div class="certificate-title">
            <h3>{{ item.title }}</h3>
            <a :href="item.link" target="_blank"
              ><img src="../assets/images/certificate.png" alt="certificare"
            /></a>
          </div>
          <div class="certificate-content">
            <div class="certificate-descripcion">
              <p>{{ item.descripcion }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import vue from "../assets/images/vue-js.svg";
import react from "../assets/images/react.svg";
import bootstrap from "../assets/images/bootstrap.svg";
import sails from "../assets/images/sails.svg";
import node from "../assets/images/nodejs.svg";
import js from "../assets/images/javascript.svg";
import css from "../assets/images/css.svg";
import html from "../assets/images/html.svg";
import email from "../assets/images/email-white.png";
import phone from "../assets/images/phone-withe.png";
import marker from "../assets/images/marker-white.png";

export default {
  name: "Cv",
  data: function () {
    return {
      tools: [
        { name: "html", img: html },
        { name: "css", img: css },
        { name: "js", img: js },
        { name: "bootstrap", img: bootstrap },
        { name: "react", img: react },
        { name: "vue", img: vue },
        { name: "node", img: node },
        { name: "sails", img: sails },
      ],

      titles: [
        {
          id: "python",
          title: "Fundamentos de python",
          link:
            "https://www.credential.net/270118a3-a899-4aac-acc8-a1bb1322caa9#gs.qghb0s",
          descripcion:
            "Orientado en el desarrollo de las bases de la programación de computadores y resolución de problemas básicos utilizando el lenguaje de programación Python. ",
        },
        {
          id: "git",
          title: "Git para proyectos",
          link:
            "https://www.credential.net/88b68fa8-d499-4150-a8e2-8edfb57443c0#gs.qgi09q",
          descripcion:
            "Abarca la identificación de las principales ventajas tales como: trabajo en equipo, mayor autonomía. estructura en árbol, sistema escalable.",
        },
        {
          id: "front",
          title: "Web Front-end",
          link:
            "https://www.credential.net/ba515955-dbb8-459f-8cf7-749444725309#gs.qgi1df",
          descripcion:
            "Uso de las tecnologias HTML, CSS, JavaScript y Bootstrap, que busca desarrollar habilidades y destrezas del desarrollo de sitios Web, que incluyen interfaces usables, atractivas, adaptativas (responsive) en cualquier tipo de dispositivo.",
        },
        {
          id: "back",
          title: "Web Back-end",
          link:
            "https://www.credential.net/b6dbab6a-a1a7-4e2e-be38-97993ca5f0c8#gs.qgi2jt",
          descripcion:
            "Enfocado en Node ya que se aprovecha el conocimiento en JavaScript para convertirse en un ambiente de programación que adapta el lenguaje, nacido para entornos Front End, en un lenguaje de uso general que puede emplearse en ambientes Back End. También exploramos el framework Sails que permite facilitar la generación de aplicaciones Web más complejas, proporcionando una estructura para la inserción de piezas de código que componen una aplicación Web para su posterior ejecución.",
        },
        {
          id: "js",
          title: "Framework Javascript",
          link:
            "https://www.credential.net/b2cd4072-3415-4633-9db7-cedf1ed037a8#gs.qgi33c",
          descripcion:
            "Se identifican los conceptos fundamentales de JavaScript. Especialmente, los conceptos necesarios para desarrollar aplicaciones Web que consuman APIs, intercambien información en formato JSON y manejen comunicación asíncrona. También se exploran dos de los frameworks más utilizados de JavaScript: React y Vue para la creación de soluciones Front End robustas usando JavaScript como lenguaje interpretado base.",
        },
        {
          id: "bases",
          title: "Bases de datos",
          link:
            "https://www.credential.net/f5e904fa-14fd-4b04-954c-5bf256c022ad#gs.qgi4kc",
          descripcion:
            "Manejo de bases de datos SQL y NoSQL usando herramientas como MySql, PostgreSQL, MongoDB y CauchDB",
        },
      ],
      contact: [
        { img: email, name: "csar-otz@live.com", cardname: "Email" },
        { img: phone, name: "(+57) 3205633553", cardname: "Celular" },
        { img: marker, name: "Santa Marta, Colombia", cardname: "Ubicacion" },
      ],
    };
  },
  props: {},
};
</script>

<style scoped>
.profile {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
.pofile-title {
  align-self: end;
  margin-left: 7.8%;
}
.information {
  display: none;
}
.photo {
  width: 100%;
  margin-bottom: 2.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.photo img {
  width: 45%;
  height: 45%;
}
.profile-content {
  border-top: solid 1px #1c1e1f;
  width: 92%;
  background: #98cbef;
  border-radius: 0px 0px 0px 1.25rem;
}
.profile-content p {
  text-align: justify;
  padding: 1.25rem 1.8125rem 1.25rem 1.25rem;
}
.studies {
  margin-top: 1.25rem;
  text-align: -webkit-right;
}
.studies h2 {
  margin-left: 7.8%;
  margin-bottom: 0.625rem;
  text-align: left;
}
.certificate {
  width: 89.5%;
  margin-bottom: 1.25rem;
}
.certificate-title {
  display: flex;
  height: 1.5rem;
}
.certificate-title h3 {
  padding-right: 1rem;
}
.certificate-title p {
  font-size: 1rem;
}
.certificate-content {
  text-align: justify;
  background: #98cbef;
  border-radius: 0px 0px 0px 1.25rem;
  padding: 1.25rem 1.8125rem 1.25rem 1.25rem;
  border-top: solid 1px #1c1e1f;
}
#bases {
  height: 13rem;
}
@media screen and (min-width: 720px) {
  .profile-content p {
    font-size: 1.1875rem;
  }
  .studies h2 {
    font-size: 1.375rem;
  }
  .studies p {
    font-size: 1.1875rem;
  }
  .certificate-title h3 {
    font-size: 1.25rem;
  }
  .certificate-title p {
    font-size: 1.1875rem;
  }
}
@media screen and (min-width: 1024px) {
  .information {
    display: block;
  }
}
</style>