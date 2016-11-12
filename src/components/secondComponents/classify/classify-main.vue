<template>
 <div class="classify">
   <classify-header :text='name' :mainshows='mainshows' :indexview='indexview'></classify-header>
   <ul>
     <li v-for='pic in pics' @click='classify("flowertea")'>
       <img :src="pic.big">
       <div class="small">
          <img :src="pic.small">
       </div>
     </li>
   </ul>
 </div>
</template>
<script>
import classifyHeader from 'components/Header'

export default {
  data() {
    return {
      name:'分类',
      pics:[
    {big:require('../../images/class03_02.jpg'),small:require('../../images/index01_03.jpg')},
    {big:require('../../images/class004.png'),small:require('../../images/class01_03.png')},
    {big:require('../../images/class003.jpg'),small:require('../../images/index01_03.jpg')},
      ]
    }
  },
  components: {
    classifyHeader
  },
  ready(){
  },
  props:{
    mainshows:Object,
    indexview:Object,
  },
  methods: {
    classify(view){
      this.indexview.preView[this.indexview.preView.length] = this.indexview.show
      this.indexview.show = view
    }
  }  
}
</script>

<style scope>
.classify li{
  position: relative;
  margin-top: 1%;
}
.classify li:nth-of-type(1){
  margin: 0;
}
.classify li img{
  width:100%;
  height:100%;
}
.classify li .small{
  height: 33.645%;
  width: 75.925%;
  position: absolute;
  top:0;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
  opacity: 0.6;
}
</style>





