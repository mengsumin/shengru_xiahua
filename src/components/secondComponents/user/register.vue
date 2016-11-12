<template>
 <div class="user-register">
   <div class="register-top">
     <form action='#' method='post'>
       <div class="username middle">
         <span>手机号码</span><input id='phone' type="text" name="phone">
       </div>
       <div class="username middle">
         <span>登录名</span><input id='username' type="text" name="username">
       </div>
       <div class="pwd middle">
         <span>密 码</span><input id="pwd" type="password" name="pwd">
       </div>
       <div class="reg-label">
         密码由6-20位英文字母、数字或符号组成
       </div>
       <div class="reg-button" @click='register'>注册</div>
     </form>
   </div>
   <alert v-ref:aler :show.sync='alerts' title="Sorry!" button-text="确定" on-hide='goLogin'>
     <p class="alerts">{{alertText}}</p>
   </alert>
 </div>
</template>
<script>
import Alert from 'vux/src/components/alert'
export default {
  data() {
    return {
      alerts:false,
      alertText:''
    }
  },
  components: {
    Alert,
  },
  ready(){
    
  },
  methods: {
    register(){
      let username = document.getElementById('username').value.trim()
      let pwd = document.getElementById('pwd').value.trim()
      if((!username)||(!pwd)){
        this.$refs.aler.title='Sorry！'
        this.alertText='用户名或密码不能为空！'
        this.alerts=true
      }else{
        if(username.length>=6&&pwd.length>=6){
          // this.$refs.aler.title='恭喜！'
          // this.alertText='注册成功！'
          // this.alerts=true  
          this.goLogin()
        }else{
         this.$refs.aler.title='Sorry！'
         this.alertText='用户名或密码格式不正确！'
         this.alerts=true  
        }
      }
    },
    goLogin(){
      this.indexview.show = 'userLogin'
    }
  },
  props:{
    mainshows:Object,
    indexview:Object,
  } 
}
</script>

<style scope>
p.alerts{
  color: black;
}
.user-register{
  height: 100vh;
  min-height: 550px;
  background: url('./images/register.jpg');
  background-size: cover;
  font-family: '微软雅黑';
}
.register-top{
  padding: 60% 0 0 0;
}
form>div{
  width: 75%;
  margin: 0.8em auto;
}
div.username,div.pwd{
  border: 1px solid white;
  padding: 0.3em 1em;
  font-size: 1.1em;
}
div.username span,div.pwd span{
  color: #b9b9b9;
  display: inline-block;
  width: 25%;
  text-align: left;
  min-width: 77px;
}
div.username input,div.pwd input{
  background: transparent;
  border: none;
  font-family: '微软雅黑';
  outline: none;
  width: 70%;
  max-width: 160px;
  font-size: 1em;
  height: 1.3em;
}
div.reg-label{
  color: white;
  margin: -0.5em auto 0;
  font-size: 0.8em;
}
div.reg-button{
  text-align: center;
  background: #f096a7;
  font-size: 1.1em;
  color: white;
  padding: 0.5em 1em;
  border-radius: 0.1rem;
}

</style>