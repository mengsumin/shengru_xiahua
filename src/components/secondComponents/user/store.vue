<template>
 <div class="store">
  <store-header :text='name' :mainshows='mainshows' :indexview='indexview'></store-header >
   <ul>
     <li v-for='info in infos'>
        <div class="show middle">
         <img :src="info.src">
         <div class="right-show">
           <p>{{info.name}}</p>
           <p class="price">¥<span>{{info.price}}</span></p>
           <button class="pay" @click='deleteone($index)'>删除</button>
         </div>
        </div>
     </li>
   </ul>
 </div>
</template>
<script>
import storeHeader from 'components/Header'
export default {
  data() {
    return {
      name:'我的收藏夹',
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
    storeHeader,
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
.store div.middle>*{
  display: inline-block;
  vertical-align: middle;
}
.store li{
  position: relative;
  height: 16.552vh;
  min-width: 340px;
  border-bottom: 1px solid rgba(0,0,0,0.5);
}
.store li>div{
  height: 100%;
}

.store div.show img{
  height: 83.797%;
  width: 38.907%;
  margin-right: 0.5rem;
}
.store button.pay{
  border: none;
  background: #f096a7;
  color: white;
  padding: 0.4em 1em;
}
.store p{
  margin: 0.3em 0;
}
</style>





