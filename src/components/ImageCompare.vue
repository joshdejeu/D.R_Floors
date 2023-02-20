<template>
  <div id="compare" @mousemove="checkPos">
    <div id="b_img_parent">
      <img class="compare_img" src="@/assets/image_compare/after.png" alt="" id="b_img">
    </div>

    <span @mousedown="checkDrag($event)" id="img_slider"></span>

    <div id="a_img_parent">
      <img class="compare_img" src="@/assets/image_compare/before.png" alt="" id="a_img">
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
    checkDrag(e){
      console.log(e.target)
      e.target.style.left = this.posX+'px';
    },
    checkPos(e){
      let aImg = document.getElementById('a_img_parent');
      let bImg = document.getElementById('b_img_parent');
      this.posX = e.pageX-105;
      let tg = document.getElementById('img_slider');
      tg.style.left = this.posX+'px';

      if(this.posX > window.innerWidth/2)
      {
        bImg.style.opacity = '0.7';
        aImg.style.opacity = '0.8';
      }else{
        aImg.style.opacity = '0.7';
        bImg.style.opacity = '0.8';
      }
      aImg.style.width = this.posX+'px';
      bImg.style.width = `calc(100% - ${this.posX}px)`;
    }
  },
  mounted() {

  }
}
</script>
  
<style scoped>
#compare {
  height: 100%; width: 100%;
  background-color: black;
  user-select: none;
  overflow: hidden;
  position: relative;
}
#b_img_parent,#a_img_parent{
  width: 100%; height: 100%;
  position: absolute; top: 0;
}
#a_img_parent{
  width: 70%;
  left: 0;
  opacity: 0.8;

}
#b_img_parent{
  width: 30%;
  right: 0;
  opacity: 0.7;
}

.compare_img{
  object-fit: cover;
  width: 100%; height: 100%;
  position: relative;
  height: 115%;
}
#b_img{
  object-position: right;
}
#a_img{
  object-position: left;
}
#img_slider{
  height: 100%; width: 10px;
  position: absolute;
  z-index: 2;
  background-color: black;
  cursor: all-scroll;
  left: 70%;
  box-shadow: inset 0px 0px 5px white;
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
  background-position: center;
  background-size: cover;
  box-shadow: inset 0px 0px 5px white;
}

@media (max-width: 1201px) {}

@media (max-width: 1025px) {}

@media (max-width: 769px) {}
</style>
  