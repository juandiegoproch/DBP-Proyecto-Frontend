<script>
export default{
    data(){
        return{
            nombre: '',
            apellido:'',
            username:'',
            correo:'',
            contrasenha:''
        }
    },
    methods:
    {
        create_user()
        {
            console.log("Se Solicito Crear Un Usuario")
            this.$emit("user_logged", {
                 username: this.username,
                 contrasenha: this.contrasenha}
                 )
        }
    }
}
</script>

<template>
    <div id="RegistryContainer">
        <div id="CosasDeRegistro">
            <h3>Crea tu cuenta!</h3>
            <hr>
            <input class="ElementoRegistro" type="text" id="nombre" name="nombre" placeholder="Ingrese su nombre" v-model="nombre"> <br>
            <input class="ElementoRegistro" type="text" id="apellido" name="apellido" placeholder="Ingrese su apellido" v-model="apellido"> <br>
            <input class="ElementoRegistro" type="text" id="username" name="username" placeholder="Ingrese su username" v-model="username"> <br>
            <input class="ElementoRegistro" type="email" id="correo" name="correo" placeholder="Ingrese su correo" v-model="correo"> <br>
            <input class="ElementoRegistro" type="password" id="passowrd" name="password" placeholder="Ingrese su contraseña" v-model="contrasenha"> <br>
            <br>
            <input type="submit" id="reg" name="reg" style="color:black" value="Registrarse" @click.prevent="create_user">
        </div>
    </div>
</template>

<style>
#CosasDeRegistro{
    background-color: antiquewhite;
    background: rgba(250, 235, 215, 0.9);
    padding: 5%;
    margin-left:  30%;
    margin-right:  30%;
    margin-top:  10%;
    text-align:center;
    font-size: medium;
    border-radius: 10px;
    text-align: center;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
.ElementoRegistro{
    padding:1%;
}
#RegistryContainer{
    text-align:center;
}
</style>