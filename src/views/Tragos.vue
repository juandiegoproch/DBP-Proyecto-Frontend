<script>
    export default{
        data(){
            let cocktail_img_url = new URL('../assets/default_image.png',import.meta.url).href
            console.log(new URL('../assets/defaul.png',import.meta.url))
            return{
                current_cocktail_img: cocktail_img_url,
                current_cocktail_name: "Loading...",
                tragos:[
                    {
                        id:1,
                        nombre:"UnimplementedT1"
                    },
                    {
                        id:2,
                        nombre:"UnimplementedT2"
                    }
                ],
                cocktails: [
                        {
                            nombre: "UnimplementedC1",
                            trago: "UnimplementedT1"
                        },
                        {
                            nombre: "UnimplementedC2",
                            trago: "UnimplementedT2"
                        }
                    ]
            }
        },
        methods:{
            changeCocktail(event)
            {
                let callername = event.target.id;
                const new_highlighted = this.cocktails.find((elem)=>{ return `cocktail_button_${elem.nombre}` === callername})
                console.log(new_highlighted.nombre)
                this.current_cocktail_name = new_highlighted.nombre;
                // los cocktails deben tener imagenes con nombre: cocktail_${new_highlighted.nombre}.png
                // en otro caso, su imagen sera la default
                if ((new URL(`../assets/cocktail_${new_highlighted.nombre}.png`,import.meta.url).href).includes('undefined'))
                {
                    this.current_cocktail_img = new URL('../assets/default_image.png',import.meta.url).href
                }
                else
                {
                    this.current_cocktail_img = new URL(`../assets/cocktail_${new_highlighted.nombre}.png`,import.meta.url).href
                }
            }
        }
    }
</script>

<template>
    <body>
        <h1>Cocktail: </h1>
        <div id="tragoContainer">
            <div id="trago">
                <div  id="cocktailImageDescriptionContainer">
                    <img :src="current_cocktail_img" style="margin:30px">
                    <p id="cocktailTitle">{{current_cocktail_name}}</p>
                </div>
                <div>
                    <h1>Estos son todos nuestros cocktails</h1>
                    <ul>
                        <li v-for="cocktail in cocktails" :key="cocktail.nombre"><button @click="changeCocktail" class="tragos_buttons" :id="`cocktail_button_${cocktail.nombre}`">{{cocktail.nombre}}</button></li>
                    </ul>
                </div>
                <div id="addCocktailContainer">
                    <h1 style="margin:1cm">No tenemos el cocktail que buscas? Añadelo!</h1>
                    <p class="inputP"> Nombre: <input type="text"> </p>
                    <p class="inputP"> Temperatura Ideal (C): <input type="number"> </p>
                    <p class="inputP"> Tolerancia (+/- C): <input type="number"> </p>
                    <p class="inputP"> Trago:
                        <select>
                            <option v-for="trago in tragos" :key="trago.id" :value="trago.id">{{trago.nombre}}</option>
                        </select>
                    </p>
                    <button @click="alert('Dummy')">Crear Cocktail</button>
                </div>
            </div>
        </div>
        
    </body>
</template>

<style>
    body
    {
        background-image:url(https://thumbs.dreamstime.com/b/divertidos-c%C3%B3cteles-de-doodle-patr%C3%B3n-sin-fisuras-lindo-estilo-c%C3%B3mic-genial-para-banners-textiles-papel-pared-envoltura-dise%C3%B1o-250614286.jpg);
    }

    #addCocktailContainer{
        display:table-row;
    }
    .inputP{
        margin-left: 1cm;
        padding-top: 3px;
    }

    #tragoContainer{
        background-color:antiquewhite;
        height: 5in;
        border-radius: 50px;
        display: flex;

    }
    #cocktailTitle{
        text-align: center;
        font-family:Verdana, Geneva, Tahoma, sans-serif;
        font: size 16px;
        padding-bottom: 1cm;
    }
    #cocktailImageDescriptionContainer{
        margin:30px;
        background-color: burlywood;
        border-radius: 20px;
    }
    #trago{
        display:flex;
    }
    .tragos_buttons{
        margin: 10px;
        padding: 7px;
        border: none;
        background: lightgray;
        border-radius: 10px;
    }
    #addCocktailContainer{
        margin:50px;
        border-radius: 30px;
        background-color:rgba(255, 127, 80, 0.25);
    }
</style>