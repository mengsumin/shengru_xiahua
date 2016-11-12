<template>
  <header class="search-header">
   <div class="search middle"></b><input type="text"><i class="search-enter"></i><span>搜索</span></div>
 </header>
</template>
<script>
module.exports = {
  components:{
  },
  data: function () {
    return {
    }
  },
  ready(){
    
  },
  methods:{
    
  },
  props:{
    
  }
}
</script>
<style scope>
  header.search-header{
    width: 100%;
    height: 7.34375vh;
    min-height: 48px;
    background: #f096a7;
    text-align: center;
  }
  .search>*{
    display: inline-block;
    vertical-align: middle;
  }
  .search{
    width: 100%;
    height: 100%;
  }
  .search>input{
    height: 55.354%;
    outline: none;
    padding-left: 3%;
    width: 62.037%;
    margin-left: 5%;
    border-width:0;
    background: url(../assets/images/search.jpg);
    background-size: 100% 100%;
  }
  .search>i{
    display: inline-block;
    height: 50.354%;
    width: 6.785%;
    border-radius: 50%;
    position: relative;
    left: -7.985%;
  }
  .search>span{
    color: white;
    font-size: 1.2em;
    position: relative;
    left: -5.585%;
  }
</style>