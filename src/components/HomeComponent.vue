<script setup>
import { ref,onMounted } from 'vue';
import BioComponent from './BioComponent.vue';
import FormComponent from './FormComponent.vue';
let screenX = window.screen.width;
let movil = screenX <= 500;
let activeMenu = ref(false);
let interval = undefined;
const bioC = ref(true);
const formC = ref(false);
const espC = ref(false);
const proyC = ref(false);
const conC = ref(false);
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


const cambioNav = (content)=>{
    const c_bio = document.getElementById("c-bio");
    const c_for = document.getElementById("c-for");
    const c_esp = document.getElementById("c-esp");
    const c_pry = document.getElementById("c-pry");
    const c_red = document.getElementById("c-red");
    let background_image = "linear-gradient(45deg, #ff0000, #ff7300, #ffeb00, #47ff00, #339353, #4d6be2, #8a00ff, #ff5050)";
    let background_size = "300% 300%";
    let background_clip = "text";
    switch (content)
    {
        case "bio":
            bioC.value = true;
            formC.value = false;
            espC.value = false;
            proyC.value = false;
            conC.value = false;
            c_bio.style.borderColor = "gray";
            c_bio.style.color = "transparent";
            c_bio.style.backgroundImage = background_image;
            c_bio.style.backgroundSize = background_size;
            c_bio.style.backgroundClip = background_clip;
            c_bio.style.padding = "0% 2.1%";
            c_for.style.borderColor = "transparent";
            c_esp.style.borderColor = "transparent";
            c_pry.style.borderColor = "transparent";
            c_red.style.borderColor = "transparent";
            c_for.style.padding = "0% 0%";
            c_esp.style.padding = "0% 0%";
            c_pry.style.padding = "0% 0%";
            c_red.style.padding = "0% 0%";
            c_for.style.color = "rgb(231, 210, 210)";
            c_esp.style.color = "rgb(231, 210, 210)";
            c_pry.style.color = "rgb(231, 210, 210)";
            c_red.style.color = "rgb(231, 210, 210)";
            break;
        case "for":
            bioC.value = false;
            formC.value = true;
            espC.value = false;
            proyC.value = false;
            conC.value = false;
            c_for.style.borderColor = "gray";
            c_for.style.padding = "0% 2.1%";
            c_for.style.color = "transparent";
            c_for.style.backgroundImage = background_image;
            c_for.style.backgroundSize = background_size;
            c_for.style.backgroundClip = background_clip;
            c_bio.style.borderColor = "transparent";
            c_esp.style.borderColor = "transparent";
            c_pry.style.borderColor = "transparent";
            c_red.style.borderColor = "transparent";
            c_bio.style.padding = "0% 0%";
            c_esp.style.padding = "0% 0%";
            c_pry.style.padding = "0% 0%";
            c_red.style.padding = "0% 0%";
            c_bio.style.color = "rgb(231, 210, 210)";
            c_esp.style.color = "rgb(231, 210, 210)";
            c_pry.style.color = "rgb(231, 210, 210)";
            c_red.style.color = "rgb(231, 210, 210)";
            break;
        case "esp":
            bioC.value = false;
            formC.value = false;
            espC.value = true;
            proyC.value = false;
            conC.value = false;
            c_esp.style.borderColor = "gray";
            c_esp.style.padding = "0% 2.1%";
            c_esp.style.color = "transparent";
            c_esp.style.backgroundImage = background_image;
            c_esp.style.backgroundSize = background_size;
            c_esp.style.backgroundClip = background_clip;
            c_bio.style.borderColor = "transparent";
            c_for.style.borderColor = "transparent";
            c_pry.style.borderColor = "transparent";
            c_red.style.borderColor = "transparent";
            c_bio.style.padding = "0% 0%";
            c_for.style.padding = "0% 0%";
            c_pry.style.padding = "0% 0%";
            c_red.style.padding = "0% 0%";
            c_bio.style.color = "rgb(231, 210, 210)";
            c_for.style.color = "rgb(231, 210, 210)";
            c_pry.style.color = "rgb(231, 210, 210)";
            c_red.style.color = "rgb(231, 210, 210)";
            break;
        case "pry":
            bioC.value = false;
            formC.value = false;
            espC.value = false;
            proyC.value = true;
            conC.value = false;
            c_pry.style.borderColor = "gray";
            c_pry.style.padding = "0% 2.1%";
            c_pry.style.color = "transparent";
            c_pry.style.backgroundImage = background_image;
            c_pry.style.backgroundSize = background_size;
            c_pry.style.backgroundClip = background_clip;
            c_bio.style.borderColor = "transparent";
            c_for.style.borderColor = "transparent";
            c_esp.style.borderColor = "transparent";
            c_red.style.borderColor = "transparent";
            c_bio.style.padding = "0% 0%";
            c_for.style.padding = "0% 0%";
            c_esp.style.padding = "0% 0%";
            c_red.style.padding = "0% 0%";
            c_bio.style.color = "rgb(231, 210, 210)";
            c_for.style.color = "rgb(231, 210, 210)";
            c_esp.style.color = "rgb(231, 210, 210)";
            c_red.style.color = "rgb(231, 210, 210)";
            break;
        case "red":
            bioC.value = false;
            formC.value = false;
            espC.value = false;
            proyC.value = false;
            conC.value = true;
            c_red.style.borderColor = "gray";
            c_red.style.padding = "0% 2.1%";
            c_red.style.color = "transparent";
            c_red.style.backgroundImage = background_image;
            c_red.style.backgroundSize = background_size;
            c_red.style.backgroundClip = background_clip;
            c_bio.style.borderColor = "transparent";
            c_for.style.borderColor = "transparent";
            c_esp.style.borderColor = "transparent";
            c_pry.style.borderColor = "transparent";
            c_bio.style.padding = "0% 0%";
            c_for.style.padding = "0% 0%";
            c_esp.style.padding = "0% 0%";
            c_pry.style.padding = "0% 0%";
            c_bio.style.color = "rgb(231, 210, 210)";
            c_for.style.color = "rgb(231, 210, 210)";
            c_esp.style.color = "rgb(231, 210, 210)";
            c_pry.style.color = "rgb(231, 210, 210)";  
    }
}

const cambioNavMovil = (content)=>{
    const c_bio = document.getElementById("c-bio-m");
    const c_for = document.getElementById("c-for-m");
    const c_esp = document.getElementById("c-esp-m");
    const c_pry = document.getElementById("c-pry-m");
    const c_red = document.getElementById("c-red-m");
    let background_image = "linear-gradient(45deg, #d667f5, #924dd2, #e050d2, #c93598, #6a1f63, #5a2578, #8a00ff, darkviolet)";
    let background_size = "300% 300%";
    let background_clip = "text";
    switch (content)
    {
        case "bio":
            bioC.value = true;
            formC.value = false;
            espC.value = false;
            proyC.value = false;
            conC.value = false;
            c_bio.style.borderColor = "gray";
            c_bio.style.color = "transparent";
            c_bio.style.backgroundImage = background_image;
            c_bio.style.backgroundSize = background_size;
            c_bio.style.backgroundClip = background_clip;
            c_bio.style.padding = "0% 2.1%";
            c_for.style.borderColor = "transparent";
            c_esp.style.borderColor = "transparent";
            c_pry.style.borderColor = "transparent";
            c_red.style.borderColor = "transparent";
            c_for.style.padding = "0% 0%";
            c_esp.style.padding = "0% 0%";
            c_pry.style.padding = "0% 0%";
            c_red.style.padding = "0% 0%";
            c_for.style.color = "rgb(231, 210, 210)";
            c_esp.style.color = "rgb(231, 210, 210)";
            c_pry.style.color = "rgb(231, 210, 210)";
            c_red.style.color = "rgb(231, 210, 210)";
            break;
        case "for":
            bioC.value = false;
            formC.value = true;
            espC.value = false;
            proyC.value = false;
            conC.value = false;
            c_for.style.borderColor = "gray";
            c_for.style.padding = "0% 2.1%";
            c_for.style.color = "transparent";
            c_for.style.backgroundImage = background_image;
            c_for.style.backgroundSize = background_size;
            c_for.style.backgroundClip = background_clip;
            c_bio.style.borderColor = "transparent";
            c_esp.style.borderColor = "transparent";
            c_pry.style.borderColor = "transparent";
            c_red.style.borderColor = "transparent";
            c_bio.style.padding = "0% 0%";
            c_esp.style.padding = "0% 0%";
            c_pry.style.padding = "0% 0%";
            c_red.style.padding = "0% 0%";
            c_bio.style.color = "rgb(231, 210, 210)";
            c_esp.style.color = "rgb(231, 210, 210)";
            c_pry.style.color = "rgb(231, 210, 210)";
            c_red.style.color = "rgb(231, 210, 210)";
            break;
        case "esp":
            bioC.value = false;
            formC.value = false;
            espC.value = true;
            proyC.value = false;
            conC.value = false;
            c_esp.style.borderColor = "gray";
            c_esp.style.padding = "0% 2.1%";
            c_esp.style.color = "transparent";
            c_esp.style.backgroundImage = background_image;
            c_esp.style.backgroundSize = background_size;
            c_esp.style.backgroundClip = background_clip;
            c_bio.style.borderColor = "transparent";
            c_for.style.borderColor = "transparent";
            c_pry.style.borderColor = "transparent";
            c_red.style.borderColor = "transparent";
            c_bio.style.padding = "0% 0%";
            c_for.style.padding = "0% 0%";
            c_pry.style.padding = "0% 0%";
            c_red.style.padding = "0% 0%";
            c_bio.style.color = "rgb(231, 210, 210)";
            c_for.style.color = "rgb(231, 210, 210)";
            c_pry.style.color = "rgb(231, 210, 210)";
            c_red.style.color = "rgb(231, 210, 210)";
            break;
        case "pry":
            bioC.value = false;
            formC.value = false;
            espC.value = false;
            proyC.value = true;
            conC.value = false;
            c_pry.style.borderColor = "gray";
            c_pry.style.padding = "0% 2.1%";
            c_pry.style.color = "transparent";
            c_pry.style.backgroundImage = background_image;
            c_pry.style.backgroundSize = background_size;
            c_pry.style.backgroundClip = background_clip;
            c_bio.style.borderColor = "transparent";
            c_for.style.borderColor = "transparent";
            c_esp.style.borderColor = "transparent";
            c_red.style.borderColor = "transparent";
            c_bio.style.padding = "0% 0%";
            c_for.style.padding = "0% 0%";
            c_esp.style.padding = "0% 0%";
            c_red.style.padding = "0% 0%";
            c_bio.style.color = "rgb(231, 210, 210)";
            c_for.style.color = "rgb(231, 210, 210)";
            c_esp.style.color = "rgb(231, 210, 210)";
            c_red.style.color = "rgb(231, 210, 210)";
            break;
        case "red":
            bioC.value = false;
            formC.value = false;
            espC.value = false;
            proyC.value = false;
            conC.value = true;
            c_red.style.borderColor = "gray";
            c_red.style.padding = "0% 2.1%";
            c_red.style.color = "transparent";
            c_red.style.backgroundImage = background_image;
            c_red.style.backgroundSize = background_size;
            c_red.style.backgroundClip = background_clip;
            c_bio.style.borderColor = "transparent";
            c_for.style.borderColor = "transparent";
            c_esp.style.borderColor = "transparent";
            c_pry.style.borderColor = "transparent";
            c_bio.style.padding = "0% 0%";
            c_for.style.padding = "0% 0%";
            c_esp.style.padding = "0% 0%";
            c_pry.style.padding = "0% 0%";
            c_bio.style.color = "rgb(231, 210, 210)";
            c_for.style.color = "rgb(231, 210, 210)";
            c_esp.style.color = "rgb(231, 210, 210)";
            c_pry.style.color = "rgb(231, 210, 210)";  
    }
    activarMenu()
    document.getElementById("check-menu").checked = false;
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
        <div id="c-bio-m" v-on:click="cambioNavMovil('bio')"><h3>Biografía</h3></div>
        <div id="c-for-m" v-on:click="cambioNavMovil('for')"><h3>Formación</h3></div>
        <div id="c-esp-m" v-on:click="cambioNavMovil('esp')"><h3>Especialidades</h3></div>
        <div id="c-pry-m" v-on:click="cambioNavMovil('pry')"><h3>Proyectos</h3></div>
        <div id="c-red-m" v-on:click="cambioNavMovil('red')"><h3>Contacto</h3></div>
    </aside>
    <main>
        <nav class="contenido">
            <div id="c-bio" v-on:click="cambioNav('bio')"><h3>Biografía</h3></div>
            <div id="c-for" v-on:click="cambioNav('for')"><h3>Formación</h3></div>
            <div id="c-esp" v-on:click="cambioNav('esp')"><h3>Especialidades</h3></div>
            <div id="c-pry" v-on:click="cambioNav('pry')"><h3>Proyectos</h3></div>
            <div id="c-red" v-on:click="cambioNav('red')"><h3>Contacto</h3></div>
        </nav>
        <BioComponent v-if="bioC" />
        <FormComponent v-if="formC" />
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
                @include mixings.texto-animado;
                animation: animación-texto 6s infinite linear;
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
    color: rgb(231, 210, 210);
    & div{
        margin: 0% auto;
        border-left-style: solid;
        border-right-style: solid;
        border-color: transparent;
        transition: 1s;
        &:hover{
            cursor: pointer;
        }
    }
    #c-bio{
        padding: 0% 2.1%;
        border-color: gray;
        @include mixings.texto-animado(#ff7300, #ff8c00, #ffa500, #ffb732, #ffcc00, #ffd700, #a0f136, #acee43);
        animation: animación-texto 6s infinite linear;
    }
}
@media screen and (max-width:500px){
    aside{
        display: block;
        z-index: 10;
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
        z-index: 10;
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
        #c-bio-m{
            @include mixings.texto-animado(#d667f5, #924dd2, #e050d2, #c93598, #6a1f63, #5a2578, #8a00ff, darkviolet);
            animation: animación-texto 6s infinite linear;
        }
    }
} 
</style>