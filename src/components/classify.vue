<template>
 <div class="classify-index">
   <component :indexview='indexView' :mainshows='shows' :is="indexView.show" transition="fade" transition-mode="out-in">
   </component>
   <footerm :shows='shows' :indexview='indexView'></footerm>
 </div>
</template>
<script>
import Footerm from 'components/footer_m'
import classifyMain from 'components/secondComponents/classify/classify-main'
import flowertea from 'components/secondComponents/classify/flowertea'
import goodsBuy from 'components/secondComponents/index/goodsBuy'
export default {
  data() {
    return {
      indexView: {show:'classifyMain',preView:[]},
    }
  },
  components: {
    Footerm,
    classifyMain,
    flowertea,
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





