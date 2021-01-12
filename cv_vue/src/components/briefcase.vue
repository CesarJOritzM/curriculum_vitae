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
figure{
    display: none;
}
.work{
    display: flex;
    flex-direction: column;
    align-items: center;
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
    width: 80%;
    margin-bottom: 1.25rem;
    border-radius: 0.625rem;
    filter: drop-shadow(-2px 4px 4px #4C6577);
}
.work-card a{
    height: 100%;
}
.work-image{
    width: 100%;
    height: 70%;
}
.work-image img{
    width: 100%;
    height: 100%;
}
.work-text{
    width: 100%;
    text-align: center;
    margin: 1rem;
}
.work-text h2{
    font-size: 1rem;
}
#Vue{
    margin-bottom: 4.5rem;
}
@media screen and (min-width:360px) {
    .work-card{
        width: 20rem;
    }
    .work-image{
        height: 11.5rem;
    }
    .work-text{
        width: 100%;
        text-align: center;
        margin: 1rem;
    }
}
@media screen and (min-width: 720px){
    .work{
        height: 70rem;
    }
    .work-card{
        margin-bottom:2.4rem ;
    }
    .work-text h2{
        font-size: 1.375rem;
    }
}
@media screen and (min-width: 1024px){
    figure{
        display: block;
        text-align: center;
        margin-bottom: 3.75rem;
    }
    figure img{
        width:12.5rem;
        height: 12.5rem;
    }
    .work{
        height: auto;
        flex-wrap: wrap;
        flex-direction: row;
        justify-content: center;
    }
    .work-card{
        margin: 0rem 1.9rem 1.9rem;
    }
    #Vue{
        margin-bottom: 2rem;
    }
}
</style>
