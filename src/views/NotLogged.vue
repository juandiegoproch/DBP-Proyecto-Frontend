<script>
import Navigation from '../components/Navigation.vue'
import LoggedNavigation from '../components/NavigationLogged.vue'

export default {
    data()
    {
        // probably better ways to do this.... :/ (However this will run on load!)
        if (this.$cookies.isKey("is_logged") && this.$cookies.get("is_logged"))
        {
            this.$router.push("/recommendations")
        }

        return{
            logged: this.$cookies.isKey("is_logged")?this.$cookies.get("is_logged"):false,
            password: this.$cookies.isKey("session_auth_key")?this.$cookies.get("session_auth_key"):"",
            user: this.$cookies.isKey("uname")?this.$cookies.get("uname"):""
        }
    },
    components:
    {
        Navigation,
        LoggedNavigation
    },
    methods: {
        get_user_info(data)
        {
            this.user = data.username;
            this.password = data.contrasenha;
            let verified = false
            //TODO: check stuff over with the backend to see if stuff is okay
            verified = true //temp!

            if (verified){
                this.logged = true;
                this.$cookies.set("uname",this.user,"1d");
                this.$cookies.set("session_auth_key",this.password,"1d"); // session auth key is password FOR NOW
                this.$cookies.set("is_logged",this.logged,"1d");
                this.$router.push("/recommendations");
            }
            else
            {
                //errhandler
            }
            console.log(this.logged);
        },
        logout_handler()
        {
            this.logged = false;
        }
    }

}
</script>

<template>
    <section v-if="!logged">
        <Navigation />
        
        <RouterView @user_logged="get_user_info" />
    </section>
    <section v-else>
        <LoggedNavigation @logout="logout_handler" />

        <RouterView :password="password" :username="user" />
    </section>
</template>

<style>

</style>