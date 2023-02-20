<template>
  <div id="app_body">
    <Header/>
    <div id="color_mode" @click="colorModeToggle()">
      <img :src="require('@/assets/home/'+bg)" alt="" id="color">
    </div>
    <HomePage/>

  </div>
</template>

<script>
import HomePage from './pages/HomePage.vue'
import Header from './components/PageHeader.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    Header
  },
  props: {

  },
  data(){
    return{
      colorToggle: false,
      bg: "sun.svg",
      elementTable: {
      },

    }
  },
  methods:{
    colorModeToggle(){
      this.colorToggle = !this.colorToggle;
      if(this.colorToggle){
        this.bg = 'moon.svg';
        this.elementTable.homePageBG.className = 'colorLight';
        this.elementTable.logoText.className = 'logoTextLight';
        this.elementTable.compareTitle.className = 'textLight';
        this.elementTable.headerOp1.className = 'header_linkLight';
        this.elementTable.headerOp2.className = 'header_linkLight';
        this.elementTable.headerOp3.className = 'header_linkLight';
      }else{
        this.bg = 'sun.svg';
        this.elementTable.homePageBG.className = 'colorDark';
        this.elementTable.logoText.className = 'logoTextDark';
        this.elementTable.compareTitle.className = 'textDark';
        this.elementTable.headerOp1.className = 'header_linkDark';
        this.elementTable.headerOp2.className = 'header_linkDark';
        this.elementTable.headerOp3.className = 'header_linkDark';



      }
    }
  },
  mounted(){
    this.elementTable = {
      homePageBG: document.getElementById('home'),
      logoText: document.getElementById('home_text'),
      compareTitle: document.getElementById('compare_title'),
      headerOp1: document.getElementById('option1'),
      headerOp2: document.getElementById('option2'),
      headerOp3: document.getElementById('option3'),

    }
  }
}
</script>

<style>

body, html{
  padding: 0; margin: 0;

}
body{
  width: 100%; height: 100%;
  overflow-x: hidden;
  background-color: inherit;
}
#app_body{
  color: #2c3e50;
}
#color_mode{
  position: fixed;
  top: 10px; right: 10px;
  width: 40px; height: 40px;
  cursor: pointer;
  display: flex; justify-content: center; align-items: center;
  user-select: none;
}
#color{
  height: 50%; width: 50%;
  object-position: center;
  object-fit: cover;
}

/* width */
body::-webkit-scrollbar {
  width: 8px;
}

/* Track */
body::-webkit-scrollbar-track {
  /* background: black; */

}

/* Handle */
body::-webkit-scrollbar-thumb {
  background: #000;
  border-radius: 5px;
}

/* Handle on hover */
body::-webkit-scrollbar-thumb:hover {
  background: rgb(80,80,80);
}
</style>




<style>
/* <!-- DARK STYLES --> */
.colorDark{
  background-color: black;
}
.logoTextDark{
  color: white;
  text-shadow: -2px 2px 1px black;
}
.textDark{
  color: white;
}
/* <!-- DARK STYLES --> */
</style>

<style>
/* <!-- LIGHT STYLES --> */
.colorLight{
  background-color: white;
}
.logoTextLight{
  color: black;
  text-shadow: -2px 2px 1px white;
}
.textLight{
  color: black;
}
/* <!-- LIGHT STYLES --> */
</style>
