<template>
 <div class="waitget">
  <waitget-header :text='name' :mainshows='mainshows' :indexview='indexview'></waitget-header >
   <ul>
     <li v-for='info in infos'>
        <div class="show middle">
         <img :src="info.src">
         <div class="right-show">
           <p>{{info.name}}</p>
           <p class="price">¥<span>{{info.price}}</span></p>
           <button class="pay">确认收货</button>
         </div>
        </div>
     </li>
   </ul>
 </div>
</template>
<script>
import waitgetHeader from 'components/Header'
export default {
  data() {
    return {
      name:'待收货',
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
    waitgetHeader,
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
.waitget div.middle>*{
  display: inline-block;
  vertical-align: middle;
}
.waitget li{
  position: relative;
  height: 16.552vh;
  min-width: 340px;
  border-bottom: 1px solid rgba(0,0,0,0.5);
}
.waitget li>div{
  height: 100%;
}

.waitget div.show img{
  height: 83.797%;
  width: 38.907%;
  margin-right: 0.5rem;
}
.waitget button.pay{
  border: none;
  background: #f096a7;
  color: white;
  padding: 0.4em 1em;
}
.waitget p{
  margin: 0.3em 0;
}
</style>





