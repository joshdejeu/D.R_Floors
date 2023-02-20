<template>
    <div id="header">
        <div class="header_option">
            <a href="#" id="option1" class="header_linkDark">Services</a>
        </div>
        <div class="header_option">
            <a href="#" id="option2" class="header_linkDark">Previous Work</a>
        </div>
        <div class="header_option">
            <a href="#" id="option3" class="header_linkDark">Contact</a>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'PageHeader',
    components: {

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
#header {
    position: fixed;
    top: 0;
    left: 0;
    width: 60vw;
    height: 80px;
    z-index: 9999;
    display: flex;
    align-items: center;
    padding-left: 50px;
    gap: 2.5em;
}

.header_linkLight:visited,.header_linkLight:active,.header_linkLight{
    color: rgba(0,0,0,0.8);
    font-weight: bold;
    cursor: pointer;
    font-size: 1.2em;
    font-family: 'Alegreya Sans', sans-serif;
    text-decoration: none;
    position: relative;
    transition: 0.2s ease;
    padding: 10px;
}
.header_linkDark:visited,.header_linkDark:active,.header_linkDark{
    color: rgba(255,255,255,0.8);
    cursor: pointer;
    font-size: 1.2em;
    font-family: 'Alegreya Sans', sans-serif;
    text-decoration: none;
    position: relative;
    transition: 0.2s ease;
    padding: 10px;
}
.header_linkDark:hover{
    color: rgba(255,255,255);
}
.header_linkLight:hover{
    color: rgba(0,0,0);
}
.header_linkDark::after{
    content: '';
    position: absolute;
    bottom: 4px;
    left: 10px;
    width: 0;
    height: 1px;
    background-color: rgba(255,255,255,0.8);
    transition: 0.2s ease;
}
.header_linkLight::after{
    content: '';
    position: absolute;
    bottom: 4px;
    left: 10px;
    width: 0;
    height: 1px;
    background-color: rgba(0,0,0,0.8);
    transition: 0.2s ease;
}
.header_linkDark:hover::after{
    content: '';
    position: absolute;
    bottom: 4px;
    left: 10px;
    width: calc(100% - 20px);
    height: 1px;
    background-color: rgba(255,255,255,1);
}
.header_linkLight:hover::after{
    content: '';
    position: absolute;
    bottom: 4px;
    left: 10px;
    width: calc(100% - 20px);
    height: 1px;
    background-color: rgba(0,0,0,1);
}
.header_option{
    opacity: 0;
}
.header_option:nth-child(1){animation: moveOptions 1s 2s forwards ease-in-out;}
.header_option:nth-child(2){animation: moveOptions 1s 2.5s forwards ease-in-out;}
.header_option:nth-child(3){animation: moveOptions 1s 3s forwards ease-in-out;}

@keyframes moveOptions {
    0%{transform: translateY(-15px); opacity: 0;}
    100%{transform: translateY(0px); opacity: 1;}
}



@media (max-width: 1201px) {}

@media (max-width: 1025px) {}

@media (max-width: 769px) {}
</style>
  