<template>
 <div class="teach-detail">
   <index-header-teach :text='name' :mainshows='mainshows' :indexview='indexview'></index-header-teach>
   <div class="teach-detail-main">
     <img src="./images/teach.jpg">
     <img src="./images/teach01.jpg">
   </div>
 </div>
</template>

<script>
import indexHeaderTeach from 'components/Header'
export default {
  data() {
    return {
      name:'书签教程',
    }
  },
  components: {
    indexHeaderTeach
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





