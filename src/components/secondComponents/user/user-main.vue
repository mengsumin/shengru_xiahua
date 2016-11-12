<template>
 <div class="user">
  <user-header gredit='true' :text='name' :mainshows='mainshows' :indexview='indexview'></user-header>
   <div class="top">
     <img :src="person.imgbig">
     <div class="head" @click='go("userLogin")'>
       <img :src="person.imgsmall">
     </div>
      <span v-if='!indexview.datas.username'>请登录</span>
      <span v-else>{{indexview.datas.username}}</span>
      <span class="flag" v-if='person.flag'>{{person.flag}}</span>
   </div>
   <div class="myorder">
     <div class="order middle">
       <span></span>
       <h6>我的订单</h6>
     </div>
     <ul class="clearfix">
       <li v-for='order in orders' @click='go(order.name)'>
         <div class="handle">
           <img :src="order.src">
         </div>
         <span>{{order.info}}</span>
       </li>
     </ul>
   </div>
   <div class="myself">
     <ul>
       <li class="middle" v-for='my in myself' @click='go(my.name)'>
         <span class="img"><img :src="my.src"></span><span>{{my.info}}</span>
       </li>
     </ul>
   </div>
   <confirm :show.sync='confirm' cancel-text='取消' confirm-text='去登录' title='Sorry' @on-confirm='confirms'>
     <p style="text-align:center">您还没有登录！</p>
   </confirm>
 </div>
</template>
<script>
import userHeader from 'components/Header'
import Confirm from 'vux/src/components/confirm'
export default {
  data() {
    return {
      name:'我',
      confirm:false,
      person:{
        imgbig:require('../../images/bg_02.png'),
        imgsmall:require('../../icons/icon_ (2).png'),
        flag:""
      },
      orders:[
        {src:require("../../icons/icon_ (4).png"),info:'待付款',name:'payfor'},
        {src:require("../../icons/icon_ (3).png"),info:'待收货',name:'waitGet'},
        {src:require("../../icons/icon_ (5).png"),info:'待评价',name:'waitCom'},
      ],
      myself:[
        {src:require("../../icons/icon_ (6).png"),info:'我的收藏夹',name:'store'},
        {src:require("../../icons/icon_ (7).png"),info:'意见反馈',name:'suggestion'},
        {src:require("../../icons/icon_ (8).png"),info:'消息',name:'message'},
        {src:require("../../icons/icon_ (1).png"),info:'设置',name:'seter'},
      ]
    }
  },
  components: {
    userHeader,
    Confirm,
  },
  ready(){
  },
  methods: {
    go(view){
      if(this.indexview.datas.username||view=='seter'){
        if(view!='userLogin'){
          this.indexview.preView[this.indexview.preView.length]=this.indexview.show
          this.indexview.show = view
        }
      }else{
          this.confirm = true
      }
    },
    confirms(){
      this.indexview.preView[this.indexview.preView.length]=this.indexview.show
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
.user div.top{
  position: relative;
}
div.user img{
  width: 100%;
  height: 100%;
}
.user div.head{
  border-radius: 50%;
  overflow: hidden;
  width: 23.3333%;
  margin:-12% auto 0;
}
.user div.top span{
  width: 15%;
  text-align: center;
  display:block;
  margin: 0.5% auto 0;
}
.user div.top span.flag{
  font-size: 0.8em;
  color: #535353;
}
.order{
  height: 2em;
  padding-left: 4%;
}
.order span{
  display: inline-block;
  vertical-align: middle;
  width: 4px;
  height: 78%;
  background: #eacf9c;
}
.order h6{
  display: inline-block;
  vertical-align: middle;
  font-size: 1.2em;
  font-weight: normal;
}
.myorder ul{
  margin: 0 4%;
  padding: 1% 4% 5%;
  border-bottom: 2px solid black;
}
.myorder li{
  float: left;
  width: 33.33333%;
  text-align: center;
}
.handle{
  margin:0.2em auto;
  width: 25%;
}
.myself{
  margin: 1% 4%;
}
.myself li{
  padding: 2% 0;
  border-bottom: 1px solid black;
}
.myself li span{
   vertical-align: middle;
   display: inline-block;
}
.myself li span.img{
  width: 7%;
  margin: 0 3.5%;
}
</style>





