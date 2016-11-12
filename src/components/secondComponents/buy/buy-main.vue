<template>
 <div class="buy">
  <buy-main-header :text='name' :mainshows='mainshows' :indexview='indexview'></buy-main-header >
   <ul>
     <li v-for='info in infos'>
       <div class="body" @touchstart='startslider' @touchmove='moveslider' @touchend='endslider'>
        <div class="show middle">
         <span></span>
         <img :src="info.src">
         <div class="right-show">
           <p>{{info.name}}</p>
           <p class="price">¥<span>{{info.price}}</span></p>
           <x-number title="数量 ：" :min='0' :fillable="false" :value='info.count'></x-number>
         </div>
         </div>
         <div class="hidden middle" @click='deleteone($index)'>
           <span></span>
         </div>
       </div>
     </li>
   </ul>
   <div class="total">
     <div class="money middle">
       <span class="selected"><span></span>全选</span>
       <span class="price middle">合计：<span>¥100.00</span></span>
       <span class="pay middle">结算（<span>0</span>）</span>
     </div>
   </div>
 </div>
</template>
<script>
import $ from 'jquery'
import buyMainHeader from 'components/Header'
import XNumber from 'vux/src/components/x-number'
export default {
  data() {
    return {
      name:'购物车',
      flag:{
        startX:0,//标记第一次触摸位置
        current:0,//当前随滑动而改变的位置
      },
      infos:[
        {
          src:require('../../images/buy_03 (1).jpg'),
          name:'生如夏花家装干花小雏菊',
          price:'130.00',
          count:1
        },
        {
          src:require('../../images/buy_03 (2).jpg'),
          name:'生如夏花浪漫漫天屋',
          price:'450.00',
          count:1
        },
        {
          src:require('../../images/buy_03 (3).jpg'),
          name:'生如夏花艺术花瓶',
          price:'666.00',
          count:1
        },
        {
          src:require('../../images/buy_03 (4).jpg'),
          name:'生如夏花混搭薰衣草',
          price:'240.00',
          count:1
        },
        {
          src:require('../../images/buy_03 (1).jpg'),
          name:'生如夏花家装干花小雏菊',
          price:'380.00',
          count:1
        }
      ]
    }
  },
  components: {
    buyMainHeader,
    XNumber
  },
  props:{
    mainshows:Object,
    indexview:Object,
  },
  ready(){
    
  },
  methods: {
    deleteone(index){
       this.infos.splice(index,1)
    },
    startslider(event){
      let touch = event.touches[0] //获取第一个触点 
      this.flag.startX = touch.pageX
      this.flag.current = Number.parseInt($(event.currentTarget).css('left'))
    },
    moveslider(event){
      let touch = event.touches[0] //获取第一个触点  
      let x = Number(touch.pageX) //页面触点X坐标  
      this.flag.screenWidth = Number.parseInt(screen.width);//屏幕宽度
      if(x - this.flag.startX<0&&x - this.flag.startX>-this.flag.screenWidth*0.22&&this.flag.current==0){
        $(event.currentTarget).css({'left': (x - this.flag.startX)})
      }else if(x - this.flag.startX>0&&x - this.flag.startX<this.flag.screenWidth*0.22&&this.flag.current<0){
        $(event.currentTarget).css({'left': (this.flag.current+x -this.flag.startX)})
      }else{
        return
      }
    },
    endslider(event){
      let left = Number.parseInt($(event.currentTarget).css('left'))
      if(this.flag.current > left){
        $(event.currentTarget).css({'left': '-22%'})
      }else if(this.flag.current < left){
        $(event.currentTarget).css({'left': '0'})
      }
    },
  }  
}
</script>

<style scope>
 .buy div.middle>*,div.money>span{
  display: inline-block;
  vertical-align: middle;
}
.buy li{
  position: relative;
  height: 16.552vh;
  width: 100%;
  overflow: hidden;
  border-bottom: 1px solid rgba(0,0,0,0.5);
}
.buy div.body{
  width: 200%;
  height: 100%;
  position: absolute;
  left: 0;
}
.buy li>div>div{
  width: 50%;
  height: 100%;
  position: absolute;
  left: 0;
}
.buy li div.hidden{
  width: 11%;
  background: red;
}
.buy li div.hidden{
  left: 50%;
}
.buy div.show img{
  height: 83.797%;
  width: 35.907%;
}
div.show>span,div.money>span:first-of-type span{
  width: 1.1em;
  height: 1.1em;
  margin: 0 2%;
  border: 1px solid rgba(0,0,0,0.5);
  border-radius: 50%;
}
.buy div.show .weui_cell::before{
  border:none;
}
div.hidden span{
  width: 2.5em;
  height: 2.5em;
  margin:auto;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url(../../images/delete_03.jpg);
  background-size: 100%;
}
div.right-show>*{
  padding: 0.15em;
  font-size: 1em;
  font-weight: 500;
}
div.right-show p.price{
  color: red;
}
div.right-show p.price span{
  padding-left: 4px;
}
.total{
  height: 8.6041vh;
}
.total .money{
  width: 100%;
  height: 8.6041%;
  position: fixed;
  bottom: 8.6041%;
  background-color: white;
}
div.money>span.selected span{
  display: inline-block;
  vertical-align: middle;
}
span.selected{
  width: 25%;
}
span.price{
  margin: -1% 0 0 15%;
}
span.price span{
  color: red;
}
span.pay {
  margin: -1.5% 0 0 0;
  color:white;
  background: #f97728;
  height: 1.6em;
  padding: 0.55em 0 0.3em 0.4em;
  border-radius: 0.4em;
}
div.money>span:first-of-type span{
  margin: -3% 12% 0 8%;
}
</style>





