<script>
export default{
    data()
    {
        //console.log(this.$cookies.keys())
        let recname  = "Unimplemented";
        let product  = "Unimplemented";
        let provider = "Unimplemented";
        let rec_img_url = new URL('../assets/default_image.png',import.meta.url).href
        let prod_img_url = new URL('../assets/default_image.png',import.meta.url).href
        let prov_img_url = new URL('../assets/default_image.png',import.meta.url).href

        // TODO talk with the backend
        // Setear las cosas de forma apropiada

        return {
            username: this.$cookies.get("uname"),
            auth_key: this.$cookies.get("session_auth_key"),
            recommended:{
                recommendation_name: recname,
                product_name: product,
                provider_name: provider,
                recommendation_img: rec_img_url,
                product_img: prod_img_url,
                provider_img: prov_img_url,
                description:""
            }
        }
    },
  computed:
  {

  }
  
}
</script>

<template>
    <body>
        <div id="Carnecita">
            <div id="RecomendacionTexto">
                <div class="Bienvenida">
                    <h1 style="padding:10px">Hola {{username}}!</h1>
                </div>
                <p id="Recommedation"> Nuestra recomendacion de hoy es {{recommended.recommendation_name}}</p>
                <hr>
                <p id="RecommendationDescription"> {{recommended.description}} </p>
                <hr>
                <p id="AsociateMarketing"> Este cocktail se hace con {{recommended.product_name}} {{recommended.provider_name}}</p>
                <div id="ProductImages">
                    <img class="ProductImage" :src="recommended.product_img">
                    <img class="ProductImage" v-if="recommended.provider_name != '' " :src="recommended.provider_img">
                </div>
            </div>
            <div class="vl"></div>
            <div id="CocktailImageContainer">
                <img id="CocktailImage" :src= "recommended.recommendation_img" />
            </div>
        </div>
    </body>
</template>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@600&display=swap');

    #CocktailImageContainer{
        width:7in;
        padding-right:2.2in;
    }

    #RecomendacionTexto{
        width:50%;
        padding-left:2%;
    }

    .Bienvenida
    {
        background-color: azure;
        text-align:center;
        font-size:large;
        font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        color:rgb(33, 33, 33);
        border-radius: 10% / 50%;
    }
    #Recommedation{
        font-size:16pt;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }
    .vl {
        border-left: 1px solid gray;
        height: 500px;
        margin-top: 2%;
        margin-bottom: 2%;
        margin-right: 1%;
        margin-left: 7%;
    }
    #ProductImages{
        display: flex;
        text-align:center;
    }

    .ProductImage{
        margin: 3%;
        width: 300px;
        height: 300px;
    }

    #Carnecita
    {
        display: flex;
        border-radius: 25px;
        width: fit-content;
        background-blend-mode:hue;
        background-color: antiquewhite;
        background: rgba(250, 235, 215, 0.9);
    }

    #CocktailImage{
        padding-top:5%;
        padding-left: 5%;
        width: 500px;
        height: 500px;

    }

</style>