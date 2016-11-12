<template>
 <div class="buy-index">
   <component :indexview='indexView' :mainshows='shows' :is="indexView.show" transition="fade" transition-mode="out-in">
   </component>
   <footerm :shows='shows' :indexview='indexView'></footerm>
 </div>
</template>
<script>
import Footerm from 'components/footer_m'
import buyMain from 'components/secondComponents/buy/buy-main'

export default {
  data() {
    return {
      indexView: {show:'buyMain',preView:[]},
    }
  },
  components: {
    Footerm,
    buyMain,
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





