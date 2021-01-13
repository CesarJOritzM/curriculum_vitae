<template>
  <div id="contact-me">
    <div class="title">
      <h1>Contactame</h1>
    </div>
    <div
      class="contact-card"
      v-for='(item, index) in data'
      :key='index'
      :id='item.cardname'
    >
      <div class="img">
        <img :src='item.img' :alt='item.cardname' />
      </div>
      <div class="text">
        <h2>{{ item.cardname }}</h2>
        <p>{{ item.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import email from "../assets/images/email.svg";
import phone from "../assets/images/phone.svg";
import location from "../assets/images/location.svg";

export default {
  name: "ContactMe",
  data: function () {
    return {
      data: [
        { img: email, name: "csar-otz@live.com", cardname: "Email" },
        { img: phone, name: "(+57) 3205633553", cardname: "Celular" },
        { img: location, name: "Santa Marta, Colombia", cardname: "Ubicacion" },
      ],
    };
  },
  props: {},
};
</script>

<style scoped>
#contact-me {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  height: 100%;
}
.contact-card {
  display: flex;
  align-items: center;
  justify-content: center;
  background: #98cbef;
  width: 84%;
  height: 6.25rem;
  margin-bottom: 2.5rem;
  border-radius: 1.25rem;
  filter: drop-shadow(-5px 10px 4px #4c6577);
  padding-right: 0.625rem;
  border: 1px solid rgba(60, 81, 95, 0.5);
}
.img {
  width: 3.75rem;
  height: 3.75rem;
  padding-right: 1rem;
}
.img img {
  width: 100%;
  height: 100%;
}
.text h2 {
  font-size: 1.25rem;
}
#Ubicacion {
  margin-bottom: 5rem;
}
@media screen and (min-width: 360px) {
  .contact-card {
    width: 18.875rem;
  }
}
@media screen and (min-width: 720px) {
  .contact-card {
    width: 34.8125rem;
    height: 10rem;
    justify-content: initial;
  }
  .text h2 {
    font-size: 1.375rem;
  }
  .text p {
    font-size: 1.2rem;
  }
  .img {
    width: 6.25rem;
    height: 6.25rem;
    padding-right: 2rem;
    padding-left: 5rem;
  }
}
</style>