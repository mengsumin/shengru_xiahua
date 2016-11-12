<template>
 <header class="clearfix middle header" @click='goback'>
   <span>&lt;</span>
   <b class="content">{{text}}</b>
   <span v-if='gredit'></span>
   <span class="search" v-if='search'></span>
   <span class="buy" v-if='buy'></span>
 </header>
</template>
<script>
export default {
  data() {
    return {
    }
  },
  props: {
    text:String,
    gredit:String,
    search:String,
    buy:String,
    mainshows:Object,
    indexview:Object,
  },
  ready(){
  },
  methods: {
    goback(){
      let bigLength=this.indexview.preView.length
      let smallLength=this.mainshows.preView.length
      if(bigLength){
        this.indexview.show=this.indexview.preView[bigLength-1]
        this.indexview.preView.pop()
      }else if(smallLength){
        this.mainshows.show=this.mainshows.preView[smallLength-1]
        this.mainshows.checked=this.mainshows.preChecked[smallLength-1]
        this.mainshows.preView.pop()
        this.mainshows.preChecked.pop()
      }
    }
  }  
}
</script>

<style scope>
header.header{
  height: 2em;
  min-height: 45px;
  text-align: center;
  font-size: 1.5em;
  background: #f096a7;
  color: white;
}
header.header span{
  float: left;
  font-size: 1.4em;
  color: white;
  margin: 0.15em 0 0 0.6em;
}
header.header span:nth-of-type(2){
  float: right;
  width: 1.4em;
  height: 1em;
  margin: 0.2em -0.6em 0 0;
  position: relative;
  left: -0.9em;
  background: url(./images/gredit_03.png) no-repeat;
  background-size: 90% 90%;
}
header.header span.search,header.header span.buy{
  float: right;
  width: 1.2em;
  height: 1em;
  margin: 0.15em -0.6em 0 0;
  position: relative;
  left: -1.2em;
  background: url(./icons/search_03.jpg) no-repeat;
  background-size: 100% 100%;
}
header.header span.buy{
  background: url(./icons/buy11.png) no-repeat;
  background-size: 85% 85%;
}
header.header b{
  font-weight: normal;
  font-size: 1.1rem;
  display: inline-block;
  width: 60%;
  margin: 0.4em 0 0 0;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>





