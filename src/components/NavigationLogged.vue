<script>
export default
{
    methods:
    {
        logout()
        {
            // TODO speak w backend to log out ... 
            this.$cookies.remove("is_logged")
            this.$cookies.remove("session_auth_key")
            this.$cookies.remove("uname")

            console.log("User logged out.")

            this.$router.push("/")

            this.$emit("logout")
        }
    }
}
</script>

<template>
    <div class="navigation">
        <RouterLink to="/tragos" class="nav-component">| Tragos |</RouterLink>
        <RouterLink to="/recommendations" class="nav-component">| Recomendaciones |</RouterLink>
        <input class="nav-component" id="logout" type = "button" @click.prevent="logout" value="Cerrar Sesion">
    </div>
</template>

<style scoped>
.navigation{
    border-radius: 10%;
    width:100%;
    display:flex;
    background-color: white;
    height:7vh;
    align-items: center;
    top:0px;
    left:0px;
}
.nav-component
{
    padding-right: 15%;
    padding-left: 10%;
    padding-top: 0.7%;
    padding-bottom: 0.7%;
    white-space: nowrap;
    text-decoration:none;
    color: black;
    font-family:'Courier New', Courier, monospace;


}
.nav-component:hover
{
    background-color:rgb(203, 203, 203);
}
#logout{
    margin-left:3%;
    padding-right: 5%;
    padding-left: 5%;
    padding-top: 0.7%;
    padding-bottom: 0.7%;
    border: none;
    width: fit-content;
    background-color:antiquewhite;
}
#logout:hover{
    background-color:gray;
}
</style>

