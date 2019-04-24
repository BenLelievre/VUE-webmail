<template>
  <div id="app">
    <p>Connecter en tant que : {{ user }}</p>
    <topbar @changeUser="changeUser"/>

    <div id="list">
     <ListMessages :user="user" @detailler="detailler"/>
     <Droite :msg="msg"/>
    </div>
 </div>
</template>

<script>
import Topbar from './components/Topbar.vue';
import ListMessages from './components/ListMessages.vue';
import Droite from './components/Droite.vue';
    export default {
    name: 'App',
    components: {
        Topbar,
        ListMessages,
        Droite,
    },
    data(){
      return {user:"",msg:{}}
    },
    methods:{
      changeUser(user)
      {
        this.user=user
      },
      detailler(msg){
        this.msg=msg
      }
    }
  }
</script>
