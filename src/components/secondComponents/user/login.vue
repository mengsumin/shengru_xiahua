<template>
 <div class="user-login">
   <div class="login-top">
     <form action='#' method='post'>
       <div class="username middle">
         <span>登录名</span><input v-model='username'type="text" name="username">
       </div>
       <div class="pwd middle">
         <span>密 码</span><input v-model="pwd" type="password" name="pwd">
       </div>
       <div class="label clearfix">
         <span class="left"><i></i>记住密码</span>
         <span class="right" @click='go("forgetPwd")'>忘记密码?</span>
       </div>
       <div class="button clearfix">
         <div class="login left" @click='login'>登录</div>
         <div class="register right" @click='register'>注册</div>
       </div>
     </form>
   </div>
   <div class="bottom">
     <divider><span class="divider">其他方式</span></divider>
     <ul class="clearfix">
       <li><a href="##"><img src="./images/user (2).jpg"></a></li>
       <li><a href="##"><img src="./images/user (1).jpg"></a></li>
       <li><a href="##"><img src="./images/user (1).png"></a></li>
     </ul>
   </div>
   <alert :show.sync='alerts' title="Sorry!" button-text="确定">
     <p class="alerts">账户名密码不匹配!</p>
   </alert>
 </div>
</template>
<script>
import Alert from 'vux/src/components/alert'
import Divider from 'vux/src/components/divider'
export default {
  data() {
    return {
      alerts:false,
      username:'',
      pwd:''
    }
  },
  components: {
    Alert,
    Divider,
  },
  ready(){
    
  },
  methods: {
    login(){
      let username = this.username
      let pwd = this.pwd
      if((!username)||(!pwd)){
        document.querySelector('p.alerts').innerText='用户名或密码不能为空！'
        this.alerts=true
      }else{
        if(username.length>=6&&pwd.length>=6){
        this.indexview.datas.username = username
        this.indexview.show = this.indexview.preView[this.indexview.preView.length-1]
        }else{
         document.querySelector('p.alerts').innerText='用户名或密码不匹配！'
         this.alerts=true  
        }
      }
    },
    register(){
      this.indexview.show = 'Register'
    },
    go(view){
      this.indexview.preView[this.indexview.preView.length]=this.indexview.show
      this.indexview.show = view
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
.user-login{
  height: 100vh;
  min-height: 550px;
  background: url('./images/register.jpg');
  background-size: cover;
  font-family: '微软雅黑';
}
.login-top{
  padding: 60% 0 0 0;
}
form>div{
  width: 75%;
  margin: 0.8em auto;
}
div.username,div.pwd{
  border: 1px solid white;
  padding: 0.3em 1em;
  font-size: 1.25em;
}
div.username span,div.pwd span{
  color: #b9b9b9;
  display: inline-block;
  width: 25%;
  text-align: center;
  min-width: 77px;
}
div.username input,div.pwd input{
  background: transparent;
  border: none;
  font-family: '微软雅黑';
  outline: none;
  width: 70%;
  font-size: 1em;
  height: 1.3em;
  max-width: 160px;
}
div.label{
  color: white;
  margin: -1.1em auto;
  font-size: 0.8em;
}
div.label i{
  display: inline-block;
  width: 1em;
  height: 1em;
  background: url('./images/pwd.png');
  background-size:110% 110%;
  margin:0 0.5em 0 -0.9em;
  vertical-align: middle;  
}
div.button{
  margin-top: 16%;
  width: 58.426%;
  background: url("./images/aaa.jpg");
  background-size: 100% 100%;
  padding: 0.3em 1em 0.35em;
  font-size: 1.1em;
  min-width: 255px;
  color: white;
}
div.button div{
  width: 37%;
  text-align: center;
}
.bottom{
  width: 100%;
  margin-top: 20%;
}
.bottom li{
  float: left;
  width: 10%;
  margin-left: 17%;
}
.bottom  span.divider{
  color:white;
}
</style>