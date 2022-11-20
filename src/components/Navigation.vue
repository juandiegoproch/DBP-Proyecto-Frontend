<script>
</script>

<template>
    <div class="navigation">
        <RouterLink to="/login" class="nav-component">| Ingresa |</RouterLink>
        <RouterLink to="/register" class="nav-component">| Registrate |</RouterLink>
        <RouterLink to="/" class="nav-component">| Inicio |</RouterLink>
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
    white-space: nowrap;
    text-decoration:none;
    color: black;
    font-family:'Courier New', Courier, monospace;

}
</style>

