<template>
 <div class="day-rec">
   <index-header-day-rec :text='name' :mainshows='mainshows' :indexview='indexview'></index-header-day-rec>
   <div class="day-rec-main">
     <img src="./images/dayrec (1).png">
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
import indexHeaderDayRec from 'components/Header'
export default {
  data() {
    return {
      name:'本周推荐',
      infos:[
      {url:require('./images/dayrec (1).jpg'),content:'生如夏花新品玫瑰花茶',price:"556.00",amount:"881"},
      {url:require('./images/dayrec (2).jpg'),content:'生如夏花新品玫瑰花茶',price:"556.00",amount:"881"},
      {url:require('./images/hot (4).png'),content:'生如夏花新品紫色勿忘我',price:"145.00",amount:"254"},
      {url:require('./images/dayrec (3).jpg'),content:'生如夏花新品小雏菊',price:"784.00",amount:"3254"},
      {url:require('./images/dayrec (2).jpg'),content:'生如夏花新品浪漫满天星',price:"485.00",amount:"14"}
      ]
    }
  },
  components: {
    indexHeaderDayRec
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
.day-rec-main ul li{
  margin: 0.3em 0 0 0;
  width: 49.44445%;
}
.day-rec-main ul li img{
  height: 38vw;
}
.day-rec-main p{
  text-align: center;
  padding: 0.2em 0 0 0;
}
.day-rec-main p span.price{
  color: red;
}
.day-rec-main p span.mount{
  color: #787878;
  font-size: 0.8em;
}
</style>





