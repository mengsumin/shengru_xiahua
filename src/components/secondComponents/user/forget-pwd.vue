<template>
 <div class="suggestion">
  <user-suggestion-header :text='name' :mainshows='mainshows' :indexview='indexview'></user-suggestion-header >
   <div class="suggestion-main">
     <p>您的账号绑定手机151****153，你可以通过短信验证码找回</p>
     <div class="reg-button">短信验证码找回</div>
     <div class="reg-button email">用邮箱找回</div>
   </div>
 </div>
</template>
<script>
import userSuggestionHeader from 'components/Header'
export default {
  data() {
    return {
      name:'密码找回'
    }
  },
  components: {
    userSuggestionHeader,
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
.suggestion-main{
  width: 90%;
  margin: auto;
}
.suggestion-main p{
  background: #f2f2f2;
  color:#4c4c4c;
  margin: 0.8em 0;
  padding: 1rem;
}
div.email{
  margin-top: 1rem;
  color:black;
}
</style>





