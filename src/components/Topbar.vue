<template>
<div>
<connect @connect="changeUser" />
	<div id="creation_mail" >
		<form id="envoi">
			<div id="_Destinataire">
				<label for="dest">Destinataire:</label>
				<input type="text" id="dest" name="dest" style="width:100%" maxlength="20"/>
			</div>
			<div id="_Message">
				<label for="message">Message:</label>
				<input type="text" id="message" name="message"  style="width:100%" maxlength="300"/>
				<input type="submit" value="Envoyer" id="btnEnvoyer">
			</div>
		</form>
    </div>
</div>
</template>

<script>
import Connect from './Connect.vue';

export default {
  name: 'TopBar',
  components: {
    Connect,
  },
  methods:{
      changeUser(user){
          this.$emit("changeUser", user)
      }
  },

};
</script>
<style scoped>
#Connexion{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
	text-align:center;
    height: 5vh;
    box-shadow: 2px 3px 5px 0px #656565;
	padding-top:0.5%;
	padding-bottom:0.5%;
	margin-bottom:2vh;
}
#form_connexion {
    margin-top: 20;
}

#creation_mail {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    height: 10vh;
    box-shadow: 2px 3px 5px 0px #656565;
    background-color: #eee;
	margin-bottom:2vh;
}

#envoi{
    display: flex;
    flex-direction: row;
    justify-content:space-around;
    align-items: center;
    background-color: #eee;
    margin-top: 16px;
    width: 100%;
}

#_Destinataire {
    display: flex;
    flex-direction: row;
	float:left;
	width:15%
}
#_Message {
    display: flex;
    flex-direction: row;
	float:right;
	width:60%;
    height: 500%;
}

#message, #dest, #btnEnvoyer {
    margin-left: 5px;    
}

#btnEnvoyer
{
	float:right;
}

.liste_mail {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #eee;
    box-shadow: 2px 3px 5px 0px #656565;
    padding: 0vh 1vh; 
    height: 10vh;
}

#listeMail{
	float:left;
    width: 15vw;
	text-decoration:none;
	color:black;
}
ul{
	list-style:none;
	margin:0;
	padding:0;
	width:100%;
}
li{			
	width:100%;
	margin:1%;
}
html{
	font-family:calibri;
	background-color:silver;
}
</style>

