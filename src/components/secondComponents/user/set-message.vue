<template>
 <div class="set-message">
  <user-message-header :text='name' :mainshows='mainshows' :indexview='indexview'></user-message-header >
  <div class="seter-main">
    <switch title='新消息提醒' :value='true'></switch>  
    <switch title='铃声' :value='true'></switch>  
    <switch title='震动'></switch>  
  </div>
 </div>

</template>
<script>
import userMessageHeader from 'components/Header'
import Switch from 'vux/src/components/switch'
export default {
  data() {
    return {
      name:'消息提醒'
    }
  },
  components: {
    userMessageHeader,
    Switch,
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





