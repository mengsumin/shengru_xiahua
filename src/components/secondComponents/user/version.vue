<template>
 <div class="version">
  <user-message-header :text='name' :mainshows='mainshows' :indexview='indexview'></user-message-header >
  <div class="version-main">
    <img src="./images/version.png">
  </div>
 </div>
</template>
<script>
import userMessageHeader from 'components/Header'
export default {
  data() {
    return {
      name:'版本信息'
    }
  },
  components: {
    userMessageHeader,
  },
  props:{
    mainshows:Object,
    indexview:Object,
  },
  ready(){
    
  },
  methods: {
  }  
}
</script>

<style scope>
  .version-main{
    width: 92%;
    margin: auto; 
  }
</style>





