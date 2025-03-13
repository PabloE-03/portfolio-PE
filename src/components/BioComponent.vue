<template>
    <h1>BIOGRAFÍA</h1>
    <div class="content">
        <details>
            <summary>Introducción</summary>
            <h3>
                ¡Buenas! soy Pablo, un programador formado en BackEnd y FrontEnd, estoy muy apasionado en este mundo, ya que,
                puedo crear un software potente para resolver cualquier problema, mis tecnologías estrella son <b>Java</b> con <b>Spring Boot</b> y 
                <b>Vue 3</b>, también tengo experiencia y conocimientos en tecnologías como <b>NodeJS</b>, <b>Express</b>, <b>Python</b>, <b>C#</b>.
            </h3>
        </details>
        <details>
            <summary>Soft Skills</summary>
            <h3>
                Soy comunicativo, me gusta trabajar en equipo y aprender tanto de los demás como de lo que voy haciendo, considero que soy
                autodidacta ya que aprendí el desarrollo FrontEnd con <b>Vue 3</b> por mi cuenta y realizando proyectos prácticos para mejorar.
            </h3>
        </details>
        <details>
            <summary>Estado actual</summary>
            <h3>
                Actualmente estoy estudiando un Curso de Especialización en <b>Inteligencia Artificial</b> y <b>Big Data</b>, estoy muy interesado en
                este mundo además de los conocimientos que poseo en el desarrollo de software. 
            </h3>
        </details>
        <details>
            <summary>Experiencia</summary>
            <h3>
                Poseo 3 meses de experiencia como becario en la empresa Solutio, los trabajos desempeñados fueron:
                <ul>
                    <li>Mantenimiento de un servidor en <b>.NET</b>.</li>
                    <li>Diseño de funcionalidad de un formulario guardando las propiedades colocadas en el servidor de <b>.NET</b>.</li>
                    <li>Migración de datos de una tabla de <b>MySQL</b> server a una tabla más optimizada, migración realizada usando scripts de <b>Python</b> y <b>C#</b>.</li>
                </ul>
            </h3>
        </details>
        
    </div>
</template>
<style lang="scss" scoped>
@use "../assets/scss/mixings.scss" as mixings;
@import url("../assets/css/animations.css");
details,h1{
    color: rgb(165, 164, 164);
}

h1{
    font-size: 4vw;
    width: 100%;
    margin: 0% auto;
    text-align: center;
}

summary{
    width: fit-content;
    transition: 0.5s ease;
    &:hover{
        cursor: pointer;
        color: #d6daf1;
    }
}

details{
    font-size: 2vw;
    margin-top: 5%;
    text-align: justify;
    &:last-of-type{
        margin-bottom: 5%;
    }
    h3{
        width: 80%;
        font-size: 1.5vw;
        margin-left: 3%;
    }
    b:nth-child(1){
        @include mixings.texto-animado(#ff4545, #d80e00, #c26700, #f89820, #f89820, #5382a1, #007396, #3c99dc);
        animation: animación-texto 6s infinite linear;
    }
    b:nth-child(2){
        @include mixings.texto-animado(#6db33f, #87c540, #a0d641, #b9e742, #d2f843, #ebf944, #f4fa45, #ffffff);
        animation: animación-texto 6s infinite linear;
    }
    b:nth-child(3){
        @include mixings.texto-animado(#42b883, #35495e, #41b883, #34495e, #42b983, #35485e, #41b783, #34485e);
        animation: animación-texto 6s infinite linear;
    }
    b:nth-child(4){
        @include mixings.texto-animado(#00a70e,#83cd29, #8cc84b, #a0c95c, #b4c96d, #c8c97e, #dcc98f, #f0c9a0);
        animation: animación-texto 6s infinite linear;
    }
    b:nth-child(5){
        @include mixings.texto-animado(#808080, #a0a0a0, #c0c0c0, #e0e0e0, #ffffff, #e0e0e0, #c0c0c0, #a0a0a0);
        animation: animación-texto 6s infinite linear;
    }
    b:nth-child(6){
        @include mixings.texto-animado(#306998, #3776ab, #306998, #3776ab, #569eda, #dddb45, #f1ef42, #ffff00);
        animation: animación-texto 6s infinite linear;
    }
    b:nth-child(7){
        @include mixings.texto-animado(#68217a, #823196, #942cad, #b742d4, #dc6af8, #bcdbe9, #d6daf1, #ffffff);
        animation: animación-texto 6s infinite linear;
    }
}

details:nth-of-type(2){
    b:nth-child(1){
        @include mixings.texto-animado(#42b883, #35495e, #41b883, #34495e, #42b983, #35485e, #41b783, #34485e);
        animation: animación-texto 6s infinite linear;
    }
}

details:nth-of-type(3){
    b:nth-child(1){
        @include mixings.texto-animado(#ccffcc, #ccffff, #99ccff, #99ccff, #6699ff, #9966ff, #cc99ff, #e6ccff);
        animation: animación-texto 6s infinite linear;
    }
    b:nth-child(2){
        @include mixings.texto-animado(#ff7f50, #ff6347, #ff4500, #ff8c00, #ffa500, #ffd700, #ffff00, #adff2f);
        animation: animación-texto 6s infinite linear;
    }
}

ul{
    li:nth-child(1),li:nth-child(2){
        b{
            @include mixings.texto-animado(#68217a, #823196, #942cad, #b742d4, #dc6af8, #bcdbe9, #d6daf1, #ffffff);
            animation: animación-texto 6s infinite linear;
            }
    }
    li:nth-child(3){
        
        b:nth-child(1){
            @include mixings.texto-animado(#306998, #3776ab, #306998, #dddb45, #dddb45, #ff7300, #ff7300, #ff7300);
            animation: animación-texto 6s infinite linear;
        }
        b:nth-child(2){
            @include mixings.texto-animado(#306998, #3776ab, #306998, #3776ab, #569eda, #dddb45, #f1ef42, #ffff00);
            animation: animación-texto 6s infinite linear;
        }
        b:nth-child(3){
            @include mixings.texto-animado(#68217a, #823196, #942cad, #b742d4, #dc6af8, #bcdbe9, #d6daf1, #ffffff);
            animation: animación-texto 6s infinite linear;
        }
    }
}

@media screen and (max-width: 500px){
    h1{
        width: fit-content;
        font-size: 9vw;
        margin: 0% auto; 
    }
    .content{
        width: fit-content;
        text-align: justify;
    }
    details{
        width: fit-content;
        font-size: 6vw;
        margin-top: 5%;
        h3{
            width: 80%;
            font-size: 3.5vw;
            margin-left: 10%;
        }
    }
    
}
</style>