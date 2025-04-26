<template>
    <h1>FORMACIÓN</h1>
    <div class="form-oficial">
        <h2>Formación oficial</h2>
        <h3>Desarrollo de Aplicaciones Multiplataforma (DAM)</h3>
        <details>
            <summary>Conocimientos o Aptitudes aprendidas</summary>
            <ul>
                <li>Lenguaje de programación Java</li>
                <li>Lenguaje de programación Python</li>
                <li>Base de Datos MySQL</li>
                <li>Framework de Java Spring Boot</li>
                <li>Conexión de Java con MySQL usando JDBC y JPA</li>
                <li>Documentación de APIS con Swagger</li>
                <li>Creación de APIS y API REST con Spring Boot</li>
                <li>Librería Pandas (python) orientada a consultas</li>
            </ul>
        </details>
        <h3>Curso de Especialización de IA y Big Data</h3>
        <details>
            <summary>Conocimientos o Aptitudes aprendidas</summary>
            <details>
                <summary>Parte de IA</summary>
                    <ul>
                        <li>Librería Pandas (python) orientada al preprocesamiento</li>
                        <li>Librería Scikit-Learn (python) orientada a la creación de modelos y otras técnicas de preprocesamiento</li>
                        <li>Librería Matplotlib (python) orientada a la visualización de resultados en gráficas</li>
                        <li>Librería nltk (python) orientada al PLN (procesamiento de lenguaje natural)</li>
                        <li>Librería opencv (python) orientada a la visión artificial</li>
                        <li>Librería flask (python) orientada a la creación de APIS y API REST</li>
                        <li>Creación de modelos de regresión para realizar predicciones</li>
                        <li>Creación de modelos de clasificación para realizar cálculo de probabilidades</li>
                    </ul>
            </details>
            <details>
                <summary>Parte de Big Data</summary>
                <ul>
                    <li>Creación de clusters con máquinas virtuales</li>
                    <li>Instalación y uso de Apache Hadoop</li>
                    <li>Uso de las herramientas hdfs y YARN por parte de Hadoop</li>
                    <li>Instalación y uso de Apache Hive junto con Apache Hadoop</li>
                    <li>Instalación y uso de Apache Spark</li>
                    <li>Instalación y uso de Apache Kafka</li>
                    <li>Creación de ETL con Spark y Hadoop</li>
                    <li>Creación de procesamiento en Batch con Apache Hadoop y Apache Spark</li>
                    <li>Aplicación de técnicas de procesamiento en Streaming con Apache Spark</li>
                    <li>Aplicación de técnicas de procesamiento en tiempo real con Apache Spark y Apache Kafka</li>
                    <li>Visualización de datos con Qlik</li>

                </ul>
            </details>
            
        </details>
        
    </div>

</template>
<style lang="scss"  scoped>
h1{
    color: rgb(165, 164, 164);
}

.form-oficial{
    border: 5px rgb(165, 164, 164);
    border-top-style: solid;
    
}

@media screen and (max-width: 500px){

h1{
    margin-bottom: 10%;
}

.form-oficial{

    h2{
        width: fit-content;
        margin: 0% auto;
        transform: translateY(-55%);
        background-color: rgb(20, 20, 20);
        padding: 0% 5%;
    }
    details{
        margin-left: 5%;
        margin-top: 3%;
        margin-bottom: 5%;
        li{
            margin-bottom: 5%;
        }
    }
    h3:nth-child(3){
        margin-left: 5%;
        margin-bottom: 3%;
    }
}

}
</style>