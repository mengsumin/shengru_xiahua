<template>
 <div class="message">
  <user-message-header :text='name' :mainshows='mainshows' :indexview='indexview'></user-message-header >
  <div class="message-class">
    <ul>
      <li class="clearfix" v-for='info in messages'>
        <div class="img">
          <img :src='info.src'>
        </div>
        <div class="namediv">
          <p class="name">{{info.username}}</p>
          <p class="xiaoxi">{{info.content}}</p>
        </div>
      </li>
    </ul>
  </div>
 </div>
</template>
<script>
import userMessageHeader from 'components/Header'
export default {
  data() {
    return {
      name:'消息',
      messages:[
        {src:require('./images/message.jpg'),username:'生如夏花',content:'原来是这样啊！店主'},
        {src:require('./images/message.png'),username:'通知消息',content:'亲！今天记得签到啊'},
      ]
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
.message-class li{
  width: 90%;
  margin: auto;
  padding: 0.5em 0;
  border-bottom: 1px solid black;
}
.message-class .img{
  width: 22%;
  height: 20vw;
  border-radius: 50%;
  float: left;
}
.message-class .namediv{
  float: left;
}
.message-class .namediv p{
  margin-left: 2rem;
  padding: 0.4rem 0;
}
.message-class .namediv p.name{
  padding-top: 0.8rem;
  font-weight: 600;
}
.message-class .namediv p.xiaoxi{
  font-size: 0.8em;
  color: #868686;
}
</style>





