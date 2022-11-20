<script>

</script>

<template>
    <body>
        <div class="NombreEmpresa">
            <h1>Bienvenido a Tragospa'ti</h1>
        </div>
        <div id="carnecita">
            <div class="QuienesSomos">
                <h2> Recomendaciones de Cocktails a un Click de Distancia!</h2>
                <hr>
                <p> En TragosPa'Ti tomamos en cuenta el clima y tus preferencias personales para elegir el mejor Cocktail para ti</p>
                <p> Explora nuevos sabores con TragosPa'Ti</p>
            </div>
            <div class="vl"></div>
            <div id="homeImage">
                <img src="../assets/cocktail_home.jpg" />
            </div>
        </div>
    </body>
</template>

<style>
    body
    {
        background-image:url(https://thumbs.dreamstime.com/b/divertidos-c%C3%B3cteles-de-doodle-patr%C3%B3n-sin-fisuras-lindo-estilo-c%C3%B3mic-genial-para-banners-textiles-papel-pared-envoltura-dise%C3%B1o-250614286.jpg);
    }
    .NombreEmpresa{
        text-align: center;
        font-size: large;
        font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        opacity: 0;
    }
    .QuienesSomos
    {
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        padding: 3%;
    }
    
    #carnecita
    {
        display: flex;
        border-radius: 25px;
        background-blend-mode:hue;
        background-color: antiquewhite;
        background: rgba(250, 235, 215, 0.9);
    }

    #home_image
    {
        max-width:100px;
        max-height:100px;
        opacity:0;
        margin:10%;
    }

    .vl {
        border-left: 1px solid gray;
        height: 500px;
        margin-top: 2%;
        margin-bottom: 2%;
        margin-left: 1%;
        margin-right: 1%;
    }

</style>