<template>
 <div class="new-pro">
   <index-header-newpro :text='name' search='true' :mainshows='mainshows' :indexview='indexview'></index-header-newpro>
   <div class="new-pro-main">
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
import indexHeaderNewpro from 'components/Header'
export default {
  data() {
    return {
      name:'新品上市',
      infos:[
      {url:require('./images/index (1).jpg'),content:'生如夏花新品茉莉花茶',price:"100.00",amount:"1516"},
      {url:require('./images/index (1).png'),content:'生如夏花新品干枝荷花',price:"154.00",amount:"81"},
      {url:require('./images/index (4).jpg'),content:'生如夏花新品小雏菊',price:"784.00",amount:"3254"},
      {url:require('./images/index (5).jpg'),content:'生如夏花新品浪漫满天星',price:"485.00",amount:"14"},
      {url:require('./images/index (2).jpg'),content:'生如夏花新品玫瑰花茶',price:"556.00",amount:"881"},
      {url:require('./images/index (3).jpg'),content:'生如夏花新品紫色勿忘我',price:"145.00",amount:"254"},
      ]
    }
  },
  components: {
    indexHeaderNewpro
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
.new-pro-main ul li{
  margin: 0.3em 0 0 0;
  width: 49.44445%;
}
.new-pro-main ul li img{
  height: 38vw;
}
.new-pro-main p{
  text-align: center;
  padding: 0.2em 0 0 0;
}
.new-pro-main p span.price{
  color: red;
}
.new-pro-main p span.mount{
  color: #787878;
  font-size: 0.8em;
}
</style>





