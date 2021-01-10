<template>
    <div class="briefcase">
        <div class="title">
            <h1>Portafolio</h1>
        </div>
        <figure>
            <img src="../assets/images/engineer.svg" alt="ingeniero">
        </figure>
        <div class="work">
            <div class="work-card" v-for='(item,index) in work'
                :key='index'
                :id='item.name'
                ><a :href='item.link'>
                    <div class="work-image">
                        <img :src='item.image' :alt='item.name'>
                    </div>
                    <div class="work-text">
                        <h2>{{item.name}}</h2>
                    </div>
                 </a>
            </div>
        </div>
    </div>
</template>

<script>
import express from "../assets/images/trabajos.png"
import salis from "../assets/images/trabajos.png"
import react from "../assets/images/trabajos.png"
import vue from "../assets/images/trabajos.png"

export default {
  name: 'Briefcase',
  data: function (){
    return {           
      work: [{name:'Express',image:express, link:"#"},
             {name:'Salis',image:salis, link:"#"},
             {name:'React',image:react, link:"#"},
             {name:'Vue',image:vue, link:"#"}]
    }
  },
  props: {
  }
}
</script>

<style scoped>
@media screen and (min-width:320px) {
    figure{
        display: none;
    }
    .work{
        display: flex;
        flex-direction: column;
        align-items: center;
        height: 65.625rem ;
    }
    .work a {
        text-decoration: none;
        color: #1C1E1F;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .work-card{
        background: #98CBEF;
        width: 84%;
        height: 14.375rem;
        margin-bottom: 1.25rem;
        border-radius: 0.625rem;
        filter: drop-shadow(-2px 4px 4px #4C6577);
    }
    .work-image{
        width: 100%;
        height: 11.5rem;
    }
    .work-image img{
        width: 100%;
        height: 100%;
    }
    .work-text{
        margin-top: .7rem;
    }
    .work-text h2{
        font-size: 1rem;
    }
}
</style>
