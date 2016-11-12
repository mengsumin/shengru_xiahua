<template>
 <div class="set-safe">
  <user-message-header :text='name' :mainshows='mainshows' :indexview='indexview'></user-message-header >
  <div class="seter-main">
    <cell title='登录名' value='1518****713'></cell>  
    <cell title='修改密码' value='>'></cell>  
  </div>
 </div>
</template>
<script>
import userMessageHeader from 'components/Header'
import Cell from 'vux/src/components/cell'
export default {
  data() {
    return {
      name:'账号安全'
    }
  },
  components: {
    userMessageHeader,
    Cell,
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





