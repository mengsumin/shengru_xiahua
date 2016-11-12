<template>
 <div class="forgetpwd">
  <user-forgetpwd-header :text='name' :mainshows='mainshows' :indexview='indexview'></user-forgetpwd-header >
   <div class="forgetpwd-main">
     <textarea> 请输入你的电子邮箱，并输入你的反馈...</textarea>
     <div class="reg-button">发送</div>
   </div>
 </div>
</template>
<script>
import userForgetpwdHeader from 'components/Header'
export default {
  data() {
    return {
      name:'意见反馈'
    }
  },
  components: {
    userForgetpwdHeader,
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
.forgetpwd-main{
  width: 90%;
  margin: auto;
}
.forgetpwd-main textarea{
  width: 97%;
  height: 50vw;
  background: #f2f2f2;
  color:#4c4c4c;
  margin: 0.8em 0;
}
</style>





