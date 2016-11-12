<template>
 <div class="set-acount">
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
    <div class="addaccount">
      + 添加账号
    </div>
  </div>
 </div>
</template>
<script>
import userMessageHeader from 'components/Header'
export default {
  data() {
    return {
      name:'账号管理',
      messages:[
        {src:require('./images/message.jpg'),username:'一世繁华',content:'一花一世界，一叶一菩提'},
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
.addaccount{
  padding: 0.5em;
  font-family: "宋体";
  font-size: 1.1em;
  text-align: center;
  color: #f096a7;
  font-weight: 600;
}
</style>





