<template>
 <div class="set-person">
  <user-message-header :text='name' :mainshows='mainshows' :indexview='indexview'></user-message-header >
 </div>
</template>
<script>
import userMessageHeader from 'components/Header'
export default {
  data() {
    return {
      name:'编辑个人资料'
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

</style>





