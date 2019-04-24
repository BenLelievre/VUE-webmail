<template>
    <div id="Listemessages">
     <Message v-for="message in messages" :msg="message" @detailler="detailler"/>
    </div>
</template>

<script>
import Message from './Message.vue';
import axios from 'axios';
	export default {
		name: 'ListMessages',
		props:["user"],
		data()
		{
			return {messages:[]}
		},
		watch:
		{
			user(user)
			{
			if (this.user!=="") {
					this.fetchMessages(user);
				}
			},
		},
		methods:{
			async fetchMessages(user)
			{
				const response = await axios.get(`http://127.0.0.1/vue-mail/helloworld/src/components/php/liste.php?user=${user}`);
				this.messages = response.data;
            },
            detailler(msg){
                this.$emit("detailler", msg)
            }
		},
		computed:{
			async mmessages()
			{
				console.log(this.user)
				if (this.user==="") {
					return []
				}
				const response = await axios.get(`http://127.0.0.1/vue-mail/helloworld/src/components/php/liste.php?user=${this.user}`);
  				return response.data;
			}
		},
		components:{
			Message
		},
		async mmounted(){
  	//const response = await axios.get('https://jsonplaceholder.typicode.com/todos');
  	const response = await axios.get('http://127.0.0.1/vuejs_webmail/src/components/php/list.php?user=user3');
  	this.messages=response.data;
  }
}
</script>
<style>
#Listemessages{
	float:left;
    width: 25vw;
	text-decoration:none;
	color:black;
}
</style>


