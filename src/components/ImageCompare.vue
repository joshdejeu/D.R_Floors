<template>
  <div id="compare" @mousemove="checkPos">
    <div id="b_img_parent">
      <img class="compare_img" src="@/assets/image_compare/before.png" alt="" id="b_img">
    </div>

    <span id="img_slider"></span>

    <div id="a_img_parent">
      <img class="compare_img" src="@/assets/image_compare/after.png" alt="" id="a_img">
    </div>
  </div>
</template>
  
<script>

export default {
  name: 'ImageCompare',
  props: {

  },
  data() {
    return {
      posX: 0,
    }
  },
  methods: {
    checkPos(e){
      let bImg = document.getElementById('b_img_parent');
      let aImg = document.getElementById('a_img_parent');
      this.posX = e.pageX - e.currentTarget.offsetLeft-5;
      let tg = document.getElementById('img_slider');
      tg.style.left = this.posX+'px';

      if(this.posX > window.innerWidth/2)
      {
        // aImg.style.opacity = '0.7';
        // bImg.style.opacity = '0.8';
      }else{
        // bImg.style.opacity = '0.7';
        // aImg.style.opacity = '0.8';
      }
      bImg.style.width = this.posX+'px';
      aImg.style.width = `calc(100% - ${this.posX+10}px)`;
    }
  },
  mounted() {

  }
}
</script>
  
<style scoped>
#compare {
  height: 99%; width: 70%;
  background-color: black;
  user-select: none;
  overflow: hidden;
  /* overflow: visible; */
  box-shadow: 0px 0px 2px 3px white;
  position: relative;
}
#a_img_parent,#b_img_parent{
  width: 100%; height: 100%;
  position: absolute; top: 0;
}
#b_img_parent{
  width: 30%;
  left: 0;
  /* opacity: 0.8; */
}
#a_img_parent{
  width: 70%;
  right: 0; 
  /* opacity: 0.7; */
}
#b_img_parent:after{content: 'BEFORE';right: 1em;}
#a_img_parent:after{content: 'AFTER';left: 1em;}
#b_img_parent::after,#a_img_parent::after
{
  position: absolute;
  top: 0.5em;
  color: white;
  font-size: 3em;
  font-family: 'Alegreya Sans', sans-serif;
  color: white;
  z-index: 33;
  text-shadow: -2px 2px 3px rgba(0,0,0,0.5);
  font-weight: bold;
}

.compare_img{
  object-fit: cover;
  width: 100%; height: 100%;
  position: relative;
  /* height: 115%; */
}
#b_img{
  object-position: left;
}
#a_img{
  object-position: right;
}
#img_slider{
  height: 100%; width: 10px;
  position: absolute;
  z-index: 2;
  background-color: white;
  cursor: all-scroll;
  left: 30%;
  box-shadow: inset 0px 0px 5px black;
}
#img_slider::after{
  content: '';
  position: absolute;
  top: 50%;
  transform: translate(0%, -50%);
  left: -30px;
  width: 70px; height: 70px;
  background-color: red;
  border-radius: 50%;
  background-image: url('@/assets/image_compare/arrow.png');
  filter: invert(1);
  background-position: center;
  background-size: cover;
  box-shadow: inset 0px 0px 5px black;
}

@media (max-width: 1201px) {}

@media (max-width: 1025px) {}

@media (max-width: 769px) {}
</style>
  