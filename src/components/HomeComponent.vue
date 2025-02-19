<script setup>
import { useRouter } from 'vue-router';
</script>
<template>
    <header>
        <div class="portada">
            <h1>PABLO ELÍAS RUIZ CÁNOVAS</h1>
            <h2>Desarrollador Full Stack</h2>
            <img src="../assets/img/foto-perfil.png">
        </div>
    </header>
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

header,main,footer{
    // @include mixings.fondo-portada;
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
    header{
        width: 100%;
        padding-bottom: 5%;
        .portada{
            width: 100%;
            margin-top: 10%;
            color: rgb(231, 210, 210);
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
    .contenido{
        & div{
            margin: 0% auto;
            padding: 0% 2.1%;
            border-left-style: solid;
            border-right-style: solid;
            border-color: gray;
            transition: 1s;
        }
        #c-bio{
            background-color: gray;
            color: black;
        }
        #c-red{
            display: none;
        }
    }
}
</style>