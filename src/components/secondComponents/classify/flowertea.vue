<template>
 <div class="flower-tea">
   <flowertea-header :text='name' search='true' :mainshows='mainshows' :indexview='indexview'></flowertea-header >
   <div class="flower-tea-main">
     <ul class="clearfix">
       <li v-for='info in infos' :class='$index%2==0?"left":"right"'>
         <img :src='info.url' @click='go(info,"goodsBuy")'>
         <p>{{info.content}}</p>
         <p class="pay">
           <span class="price">¥{{info.price}}</span>
           <span class="mount"><span>{{info.amount}}</span>人付款</span>
         </p>
       </li>
     </ul>
   </div>
 </div>
</template>

<script>
import flowerteaHeader from 'components/Header'
export default {
  data() {
    return {
      name:'养生花茶',
      infos:[
      {url:require('./images/tea (1).png'),content:'生如夏花新品干枝荷花',price:"154.00",amount:"81"},
      {url:require('./images/tea (2).jpg'),content:'生如夏花新品玫瑰花茶',price:"556.00",amount:"881"},
      {url:require('./images/tea (4).jpg'),content:'生如夏花新品小雏菊',price:"784.00",amount:"3254"},
      {url:require('./images/tea (5).jpg'),content:'生如夏花新品浪漫满天星',price:"485.00",amount:"14"},
      {url:require('./images/tea (3).jpg'),content:'生如夏花新品紫色勿忘我',price:"145.00",amount:"254"},
      ]
    }
  },
  components: {
    flowerteaHeader
  },
  ready(){
  },
  methods: {
    go(info,view){
      this.indexview.datas = info
      this.indexview.preView[this.indexview.preView.length] = this.indexview.show
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
.flower-tea-main ul li{
  margin: 0.5em 0 0 0;
  width: 49.44445%;
}
.flower-tea-main ul li img{
  height: 38vw;
}
.flower-tea-main p{
  text-align: center;
  padding: 0.2em 0 0 0;
}
.flower-tea-main p span.price{
  color: red;
}
.flower-tea-main p span.mount{
  color: #787878;
  font-size: 0.8em;
}
</style>





