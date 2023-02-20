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
            <span id="mouse_outside" class="dark">
                <span id="mouse_ball" class="dark"></span>
                <span id="mouse_ball" class="dark"></span>
            </span>
        </div>
        <div id="compare_title" class="textDark">
            Compare Our Work
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
#compare_title{
    text-align: center;
    font-size: 5em;
    font-family: 'Alegreya Sans', sans-serif;
    padding-top: 20vh;
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
    padding-top: 15vh;
    display: flex;
    justify-content: center; align-items: center;
}
#mouse_outside{
    height: 90px;
    width: 50px;
    border-radius: 30px 30px 25px 25px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
    justify-content: start;
    border: 2px solid white;
}
#mouse_ball{
    width: 15px; height: 15px;
    border-radius: 50%;
    /* background-color: white; */
    background-image: url('@/assets/home/arrow.png');
    background-position: center;
    background-size: cover;
    opacity: 0;
    position: absolute;
    top: 0;
    margin-top: 30px;
}
#mouse_ball:nth-child(1)
{animation: scrollWheel 3s 1.5s infinite linear}
#mouse_ball:nth-child(2)
{animation: scrollWheel 3s 0s infinite linear}

.dark{

}
@keyframes scrollWheel {
    0%{transform: translateY(-30px); opacity: 0;}
    50%{transform: translateY(-10px); opacity: 1;}
    100%{transform: translateY(10px); opacity: 0;}
}



@import url('https://fonts.googleapis.com/css2?family=Alegreya+Sans:wght@300&display=swap');

@media (max-width: 1201px) {}

@media (max-width: 1025px) {}

@media (max-width: 769px) {}
</style>
  