<template>
 <div class="user-index">
   <component :indexview='indexView' :mainshows='shows' :is="indexView.show" transition="fade" transition-mode="out-in">
   </component>
   <footerm v-if='indexView.show!="userLogin"&&indexView.show!="Register"' :shows='shows' :indexview='indexView'></footerm>
 </div>
</template>
<script>
import Footerm from 'components/footer_m'
import userMain from 'components/secondComponents/user/user-main'
import userLogin from 'components/secondComponents/user/login'
import Register from 'components/secondComponents/user/register'
import payfor from 'components/secondComponents/user/payfor'
import store from 'components/secondComponents/user/store'
import waitGet from 'components/secondComponents/user/waitget'
import waitCom from 'components/secondComponents/user/waitcom'
import suggestion from 'components/secondComponents/user/suggestion'
import message from 'components/secondComponents/user/message'
import seter from 'components/secondComponents/user/seter'
import setMessage from 'components/secondComponents/user/set-message'
import setAccount from 'components/secondComponents/user/set-account'
import setPerson from 'components/secondComponents/user/set-person'
import setSafe from 'components/secondComponents/user/set-safe'
import setVersion from 'components/secondComponents/user/version'
import forgetPwd from 'components/secondComponents/user/forget-pwd'

export default {
  data() {
    return {
      indexView: {show:'userMain',preView:[],datas:{username:false}},
    }
  },
  components: {
    Footerm,
    userMain,
    userLogin,
    Register,
    payfor,
    store,
    waitGet,
    waitCom,
    suggestion,
    message,
    seter,
    setMessage,
    setAccount,
    setPerson,
    setSafe,
    setVersion,
    forgetPwd
  },
  ready(){
  },
  methods: {
  },
  props:{
    shows:Object
  }  
}
</script>
<style scope>
</style>





