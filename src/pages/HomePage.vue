<template>
    <div id="home" class="colorDark">
        <div id="home_text_container">
            <span id="home_text" class="logoTextDark">
                <span id="company">
                    <span id="aniR">D</span>
                    <span>&</span>
                    <span id="aniD">R</span>
                    <span id="space"></span>
                    <span>FLOORS</span>
                </span>


                <span id="flag_container">
                    <span id="flag_color1"></span>
                    <span id="flag_color2"></span>
                    <span id="flag_color3"></span>
                </span>
            </span>
        </div>
        <div id="scroll_icon">
            <svg 
                width="50px" viewBox="0 0 14.334 24.75" >
                <circle class="circle-1" fill="white" cx="7.167" cy="6" r="1.2"/>
                <circle class="circle-2" fill="white" cx="7.167" cy="6" r="1.2"/>
            <path stroke="white" fill="transparent" d="M7.167,0.5C3.485,0.5,0.5,3.485,0.5,7.167v10.416                   c0,3.682,2.985,6.667,6.667,6.667s6.667-2.985,6.667-6.667V7.167C13.834,3.485,10.849,0.5,7.167,0.5z"/>
            </svg>
        </div>
        <div id="compare_container">
            <ImageCompare/>
        </div>

    </div>
</template>
  
<script>
import ImageCompare from '../components/ImageCompare.vue';
export default {
    name: 'HomePage',
    components: {
        ImageCompare
    },
    props: {
        
    },
    data() {
        return {

        }
    },
    methods: {

    },
    mounted() {

    }
}
</script>
  
<style scoped>

.circle-1, .circle-2 {
  animation: scroll 2s infinite linear;
  opacity:0;
}

.circle-2{
  animation-delay: 1s;
}

@keyframes scroll {
  0% {
    cy: 4;
    opacity: 0;
  }
  45%, 55% {
    opacity: 1;
    cy: 9;
  }
  100% {
    cy: 14;
    opacity: 0;
  }
}
#scroll_icon{
    display: flex;
    justify-content: center; align-items: start;
    width: 100%;
    height: 20vh;
    opacity: 0;
    animation: 0.5s 1s showIt forwards ease ;
}
@keyframes showIt {
    0%{opacity: 0; transform: translateY(50px);}
    100%{opacity: 1;transform: translateY(0px);}
}
#aniD{
    animation: moveD 0.5s 1.5s forwards linear;
}
#aniR{
    animation: moveR 0.5s 1.5s forwards linear;
}
@keyframes moveD {
    0%{transform: translateX(0em) translateY(0);}
    25%{transform: translateX(0em) translateY(-50%);}
    50%{transform: translateX(-1.2em) translateY(-50%);}
    75%{transform: translateX(-1.2em) translateY(-0%);}
    100%{transform: translateX(-1.2em) translateY(0);}
}
@keyframes moveR {
    0%{transform: translateX(0em) translateY(0);}
    25%{transform: translateX(0em) translateY(50%);}
    50%{transform: translateX(1.3em) translateY(50%);}
    75%{transform: translateX(1.3em) translateY(0%);}
    100%{transform: translateX(1.3em) translateY(0);}
}

#space{
    height: 1em;
    width: 0.5em;
    display: flex;
}
#company{display: flex;}
#home{
    width: 100%;
    height: 100%;
    transition: 0.2s ease;
}

#home_text_container{
    width: 100%; height: 70vh;
    padding-bottom: 10vh;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 10;
    position: relative;
    pointer-events: none;
    font-size: 4em;

    font-family: 'Alegreya Sans', sans-serif;
}
#home_text{
    width: fit-content;
    height: 90px;
    animation: showTitle 1s forwards ease-in-out;
    display: flex;
    flex-direction: column;
    gap: 10px;
}
@keyframes showTitle {
    0%{transform: translateY(40px); opacity: 0;}
    30%{transform: translateY(40px); opacity: 0;}
    100%{}
}
@keyframes showFlag {
    0%{transform: translateY(40px); opacity: 0;}
    30%{transform: translateY(40px); opacity: 0;}
    100%{opacity: 1;}
}
/* @keyframes showColors {
    0%{transform: translateY(70px); opacity: 0;}
    30%{transform: translateY(70px); opacity: 0;}
    100%{opacity: 1;}
}  */
#flag_container{
    width: 100%;
    height: 100%;
    opacity: 0;
    position: relative;
    background-color: transparent;
    z-index: 55;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    animation: showFlag 0.8s 1.1s forwards ease-in-out;
}
#flag_color1{background-color: #002B7F; animation: showColors 1.3s 1s forwards ease-in-out;}
#flag_color2{background-color: #FCD116;animation: showColors 1.2s 1s forwards ease-in-out;}
#flag_color3{background-color: #CE1126;animation: showColors 1.1s 1s forwards ease-in-out;}




#compare_container{
    width: calc(100% - 200px); height: 80vh;
    padding-left: 100px;
    padding-bottom: 25vh;
    padding-top: 25vh;
    display: flex;
    justify-content: center; align-items: center;
}



@import url('https://fonts.googleapis.com/css2?family=Alegreya+Sans:wght@300&display=swap');

@media (max-width: 1201px) {}

@media (max-width: 1025px) {}

@media (max-width: 769px) {}
</style>
  