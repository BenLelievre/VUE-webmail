<template>
  <div id="Messages" @click="detailler">
    <li class="liste_mail">
			  <a id="listeMail"  >
          <div>
            <div>
              <div>
                Destinataire: {{ msg.destinataire }} Date:{{ msg.date }}
              </div>
              <div>
					      Messsage: {{ msg.message }}
              </div>
            </div>
          </div>
				</a>
			<a id="croix">
			  <span class="croixgauche"></span>
        <span class="croixdroite"></span>
		  </a>
		</li>
  </div>
</template>

<script>

export default {
  name: 'Message',
  props: ['msg'],

  methods:{
    detailler(){
      this.$emit("detailler", this.msg)
    }
  }
};
</script>
<style>

#gauche {
	float:left;
	width:30%;
	padding-left: 1vw;

}
.croixgauche,
.croixdroite {
  position: relative;
  display: block;
  height: 2px;
  width: 40px;
  border-radius: 1px;
  background: red;
}

.croixgauche {
    transform: rotate(-45deg);
    top: -1;
    right: 4;
    transform-origin: 15px 2px;
}

.croixdroite {
    transform: rotate(45deg);
    top: 9;
    right: 5;
    transform-origin: 15px 2px;
}
#listeMail{
	float:left;
    width: 25vw;
	text-decoration:none;
	color:black;
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
</style>
