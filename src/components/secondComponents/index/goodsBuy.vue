<template>
 <div class="goods">
   <index-header-goods-sell :text='name' buy='true' :mainshows='mainshows' :indexview='indexview'></index-header-goods-sell>
   <div class="goods-main">
     <div class="bigpic">
       <img :src="indexview.datas.url">
     </div>
     <div class="goods-data clearfix">
       <div class="goods-data-top clearfix">
         <div class="p">
           <p>{{indexview.datas.content}}</p>
           <p><span class="currprice">{{indexview.datas.price}}</span><span class="preprice">原价¥220.00</span></p>
         </div>
         <div class="icons clearfix">
           <div><img src="../../icons/icon (2).jpg"><span>查看评论</span></div>
           <div><img src="../../icons/icon (3).jpg"><span>分享</span></div>
         </div>
       </div>
       <div class="goods-data-choose">
         <img src="./images/goods.png">
       </div>
       <x-number :value='1' :min='0' :fillable='false' title="购买数量 ："></x-number>
       <div class="goods-data-buy">
         <img src="./images/buygoods.png">
       </div>
     </div>
   </div>
 </div>
</template>
<script>
import indexHeaderGoodsSell from 'components/Header'
import XNumber from 'vux/src/components/x-number'
export default {
  data() {
    return {
      name:this.indexview.datas.content,
    }
  },
  components: {
    indexHeaderGoodsSell,
    XNumber
  },
  ready(){
    console.log(this.indexview.datas)
  },
  methods: {
  },
  props:{
    mainshows:Object,
    indexview:Object,
  }  
}
</script>

<style scope>
.bigpic{
  width: 100%;
  height: 62vw;
}
.goods-data{
  padding: 2% 5%;
  font-family: '微软雅黑';
}
.goods-data-top {
  border-bottom: 1px solid black;
  padding-bottom: 0.5em;
}
.goods-data-top .p{
  float: left;
  width: 60%;
}
.goods-data-top .p p{
  font-size: 1.2rem;
  padding: 0.2rem 0;
}
span.currprice{
  color: red;
}
span.preprice{
  color: #969696;
  font-size: 0.6em;
  padding-left: 1em;
  text-decoration:line-through
}
.goods-data-top .icons{
  float: right;
  width: 34%;
}
.goods-data-top .icons div{
  width: 50%;
  float: left;
  text-align: center;

}
.goods-data-top .icons div img{
  width: 50%;
  height: 50%;
}
.goods-data-top .icons span{
  display:block;
  font-size: 0.8em;
  color: #969696; 
}
.goods-data-choose{
  padding: 1em 0;
}
.goods-main .weui_cell::before{
  border:none;
}
.goods-data-buy{
  padding-top: 1em;
  border-top: 1px solid black;
}
</style>





