<template>
   <component :views.sync='views' transition="fade" transition-mode="out-in" :is='views'>
   </component>
</template>

<script>
import Start from 'components/start'
import Welcome from 'components/welcome'
import App from 'components/app'
export default {
  data() {
    return {
      views:'Start'
    }
  },
  components: {
    Start,
    Welcome,
    App
  },
  ready(){
  	setTimeout(()=>this.views='Welcome',3000)
  },
  methods: {
  }  
}
</script>

<style scope>
 .start{
 	width: 100%;
 	height: 100vh;
 }
 @media screen and (min-width: 960px){
    body{
      background-color: #deead8;
    }
   .start{
    width: 500px;
    height: 700px;
    margin:auto;
   }
 }
 .start>img{
 	width: 100%;
 	height: 100%;
 }
</style>





