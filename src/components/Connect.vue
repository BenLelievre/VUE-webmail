<template>

    <div id="Connexion">
        <!--<h1>webmail {{user}}</h1>-->
            <form id="form_connexion" >
				<input type="text" maxlength="20" v-model="user" placeholder="Login"/>
				<input type="submit" value="Connexion" @click="connexion()">
			</form>
    </div>

</template>

<script>
export default {
	name: 'connect',
	components: {
	},
	methods:{
		connexion() {
                this.$emit("connect", this.user);
            }
	},
	data(){
		return{
			user:""
		};
	},
}
</script>

<style>

</style>
