<template>
 <div class="index">
   <component :indexview='indexView' :mainshows='shows' :is="indexView.show" transition="fade" transition-mode="out-in">
   </component>
   <footerm :shows='shows' :indexview='indexView'></footerm>
 </div>
</template>

<script>
import Footerm from 'components/footer_m'
import indexMain from 'components/secondComponents/index/index-main'
import hotSell from 'components/secondComponents/index/hotSell'
import newPro from 'components/secondComponents/index/newPro'
import weekRec from 'components/secondComponents/index/teach'
import teachDetail from 'components/secondComponents/index/teachDetail'
import teach from 'components/secondComponents/index/teach'
import dayRec from 'components/secondComponents/index/dayRec'
import question from 'components/secondComponents/index/question'
import goodsBuy from 'components/secondComponents/index/goodsBuy'

export default {
  data() {
    return {
      indexView: {show:'indexMain',preView:[],datas:{}},
    }
  },
  components: {
    Footerm,
    indexMain,
    newPro,
    hotSell,
    teach,
    teachDetail,
    dayRec,
    weekRec,
    question,
    goodsBuy
  },
  ready(){
  },
  methods: {
  },
  props:{
    shows:Object
  }  
}
</script>

<style scope>
</style>





