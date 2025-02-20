<script setup>
import { ref,onMounted } from 'vue';

 
let screenX = window.screen.width;
let movil = screenX <= 500;
let activeMenu = ref(false);
let interval = undefined;
const checkScreen = ()=>{
    screenX = window.screen.width;
    movil = screenX <= 500;
}

const activarMenu = () => {
    activeMenu.value = !activeMenu.value;
    let menu = document.getElementById("menu-content");
    let main = document.getElementsByName("main");
    let portada = document.getElementsByClassName("portada")[0]; 
    if(activeMenu.value){
        menu.style.left = "0%";
        portada.style.opacity = "0.2";
    }
    else
    {
        menu.style.left = "-60%";
        portada.style.opacity = "1";
    }
}


onMounted(()=>{
    interval = setInterval(checkScreen(),50);
})
</script>
<template>
    <header>
        <nav class="contenido-movil">
            <div class="boton">
                <input type="checkbox" id="check-menu"  v-on:click="activarMenu">
                <div class="barra-menu"></div>
                <div class="barra-menu"></div>
                <div class="barra-menu"></div>
            </div>
        </nav>
        <div class="portada">
            <h1>PABLO ELÍAS RUIZ CÁNOVAS</h1>
            <h2>Desarrollador Full Stack</h2>
            <img src="../assets/img/foto-perfil.png">
        </div>
    </header>
    <aside id="menu-content">
        <div id="c-bio"><h3>Biografía</h3></div>
        <div id="c-for"><h3>Formación</h3></div>
        <div id="c-esp"><h3>Especialidades</h3></div>
        <div id="c-pry"><h3>Proyectos</h3></div>
        <div id="c-red"><h3>Contacto</h3></div>
    </aside>
    <main>
        <nav class="contenido">
            <div id="c-bio"><h3>Biografía</h3></div>
            <div id="c-for"><h3>Formación</h3></div>
            <div id="c-esp"><h3>Especialidades</h3></div>
            <div id="c-pry"><h3>Proyectos</h3></div>
            <div id="c-red"><h3>Contacto</h3></div>
        </nav>
    </main>
    <footer>

    </footer>
      
    
</template>
<style scoped lang="scss">
@use "../assets/scss/mixings.scss" as mixings;
@import url("../assets/css/animations.css");

aside{
    display: none;
}
#check-menu{
    display: none;
}
header{
    width: 100%;
    height: fit-content;
    border-color: rgb(56, 52, 56);
    border-bottom-style: solid;
    text-align: center;
    border-width: 5px;
    .portada{
            width: 100%;
            margin: 0% auto;
            color: rgb(231, 210, 210);
            h1{
                font-size: 3vw;
            }
            h2{
                font-size: 2.5vw;
                color: transparent;
                background-image: linear-gradient(45deg, #ff0000, #ff7300, #ffeb00, #47ff00, #339353, #4d6be2, #8a00ff, #ff5050);
                background-size: 300% 300%;
                background-clip: text;
                animation: animación-texto-portada 6s infinite linear;
            }
            img{
                width: 20%;
                border-radius: 50%;
                border: solid dimgray 4px;
                margin-top: 2%;
            }
        }
}
.contenido{
    width: 100%;
    height: fit-content;
    background-color: rgb(44, 42, 44);
    display: flex;
    text-align: center;
    & div{
        margin: 0% auto;
        border-left-style: solid;
        border-right-style: solid;
        border-color: transparent;
        transition: 1s;
        &:hover{
            padding: 0% 2.1%;
            border-color: gray;
            cursor: pointer;
        }
    }
    #c-bio{
        background-color: gray;
        color: black;
        padding: 0% 2.1%;
    }
}
@media screen and (max-width:500px){
    aside{
        display: block;
    }
    #check-menu{
        display: inline-block;
    }
    .contenido{
        display: none;
    }
    header{
        width: 100%;
        padding-bottom: 5%;
        border-width: 10px;
        .portada{
            width: 100%;
            margin-top: 20%;
            color: rgb(231, 210, 210);
            transition: 0.5s;
            img{
                width: 45%;
                border-radius: 50%;
                border: solid dimgray 4px;
                margin-top: 7%;
            }
            h1{
                font-size: 6vw;
            }
            h2{
                font-size: 5.5vw;
            }
        }
    }
    .contenido-movil{
        width: 100%;
        padding: 4% 0%;
        height: fit-content;
        background-color: rgb(63, 62, 62);
        position: fixed;
        top: 0%;
        text-align: left;
        .barra-menu{
            position: absolute;
            width: 8%;
            height: 5%;
            margin-top: 5%;
            background-color: rgb(231, 210, 210);
            transition: 0.3s cubic-bezier(0.37, -1.11, 0.79, 2.02);
            // posiciones para el bucle for
            $left: 3%;
            $top: -30%;
            // recorrido de las barras del menu
            @for $i from 1 to 4{
                &:nth-of-type(#{$i}){
                    $top: $top + 20%;
                    top: $top;
                    left: $left;
                }
            }
        }
        #check-menu{
            transform: scale(4,3.5) translate(35%,5%);
            opacity: 0;
            &:checked ~ .barra-menu:nth-of-type(1){
                transform: translateY(450%) rotate(45deg);
            }
            &:checked ~ .barra-menu:nth-of-type(2){
                opacity: 0;
            }
            &:checked ~ .barra-menu:nth-of-type(3){
                transform: translateY(-350%) rotate(-45deg);
            }
        }
    }
    #menu-content{
        position: fixed;
        width: 60%;
        height: 100%;
        top: 6.8%;
        left: -60%;
        background-color: rgb(29, 34, 34);
        transition: 0.5s ease-in-out;
        div{
            margin: 5%;
            margin-top: 10%;
            width: fit-content;
            font-size: 5vw;
        }
    }
} 
</style>