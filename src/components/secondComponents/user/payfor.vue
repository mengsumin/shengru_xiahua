<template>
 <div class="payfor">
  <payfor-header :text='name' :mainshows='mainshows' :indexview='indexview'></payfor-header >
   <ul>
     <li v-for='info in infos'>
        <div class="show middle">
         <img :src="info.src">
         <div class="right-show">
           <p>{{info.name}}</p>
           <p class="price">¥<span>{{info.price}}</span></p>
           <button class="delete" @click='deleteone($index)'>删除订单</button>
           <button class="pay">付款</button>
         </div>
        </div>
     </li>
   </ul>
 </div>
</template>
<script>
import payforHeader from 'components/Header'
export default {
  data() {
    return {
      name:'待付款',
      infos:[
        {
          src:require('../../images/buy_03 (1).jpg'),
          name:'生如夏花家装干花小雏菊',
          price:'130.00',
        },
        {
          src:require('../../images/buy_03 (2).jpg'),
          name:'生如夏花浪漫漫天屋',
          price:'450.00',
        },
        {
          src:require('../../images/buy_03 (3).jpg'),
          name:'生如夏花艺术花瓶',
          price:'666.00',
        }
      ]
    }
  },
  components: {
    payforHeader,
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
    }
  }  
}
</script>

<style scope>
.payfor div.middle>*{
  display: inline-block;
  vertical-align: middle;
}
.payfor li{
  position: relative;
  height: 16.552vh;
  min-width: 340px;
  border-bottom: 1px solid rgba(0,0,0,0.5);
}
.payfor li>div{
  height: 100%;
}
.payfor div.show img{
  height: 83.797%;
  width: 38.907%;
  margin-right: 0.5rem;
}
.payfor button{
  border: none;
  background: transparent;
  padding: 0.3em;
}
.payfor button.delete{
  border: 1px solid black;
}
.payfor button.pay{
  background: #f096a7;
  color: white;
  padding: 0.4em 1em;
}
.payfor p{
  margin: 0.3em 0;
}
</style>





