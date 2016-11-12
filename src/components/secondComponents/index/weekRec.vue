<template>
 <div class="week-rec">
   <index-header-rec :text='name' :mainshows='mainshows' :indexview='indexview'></index-header-rec>
   <div class="week-rec">
     <img src="./images/rec.jpg">
     <img src="./images/rec.png">
   </div>
 </div>
</template>

<script>
import indexHeaderRec from 'components/Header'
export default {
  data() {
    return {
      name:'书签教程',
    }
  },
  components: {
    indexHeaderRec
  },
  ready(){
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

</style>





