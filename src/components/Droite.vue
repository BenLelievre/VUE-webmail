<template>
  <div id="droite">
   {{msg.message}}
  </div>
</template>

<script>

export default {
  name: 'Droite',
  props: ['msg']
};
</script>
<style>
#droite {
	float:right;
	width:55%;
	background-color:rgb(192, 192, 192);
	height:75%;
  box-shadow: 2px 3px 5px 0px #656565;
	padding-left:5%;
	padding-right:5%;
}
</style>
