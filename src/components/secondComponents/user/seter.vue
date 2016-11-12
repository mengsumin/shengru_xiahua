<template>
 <div class="seter">
  <user-seter-header :text='name' :mainshows='mainshows' :indexview='indexview'></user-seter-header >
  <div class="seter-main">
    <cell title='账号安全' value='>' @click='go("setSafe")'></cell>  
    <cell title='个人资料' value='>' @click='go("setPerson")'></cell>  
    <cell title='账号管理' value='>' @click='go("setAccount")'></cell>  
    <cell title='消息提醒' value='>' @click='go("setMessage")'></cell>  
    <cell title='版本信息' value='1.6.3 >' @click='go("setVersion")'></cell>  
  </div>
 </div>
</template>
<script>
import userSeterHeader from 'components/Header'
import Cell from 'vux/src/components/cell'
export default {
  data() {
    return {
      name:'设置'
    }
  },
  components: {
    userSeterHeader,
    Cell,
  },
  props:{
    mainshows:Object,
    indexview:Object,
  },
  ready(){
    
  },
  methods: {
    go(view){
      this.indexview.preView[this.indexview.preView.length]=this.indexview.show
      this.indexview.show = view
    }
  }  
}
</script>

<style scope>
.seter-main{
  font-family: sans-serif;
  width: 90%;
  margin: auto;
  font-weight: 500;
}
.weui_cell{
  border-bottom: 1px solid black;
}
</style>





