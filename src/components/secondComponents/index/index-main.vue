<template>
 <div class="index-main">
   <search></search>
   <div class="recommend" @click='rec("weekRec")'>
     <div class="hot">
       <p class="middle">生如夏花干花店本期主打</p>
       <p class="middle">论花瓶的重要性</p>
     </div>
   </div>
   <nav>
     <div class="nav">
       <ul class="clearfix">
         <li class="middle" @click='indexClick' v-for='nav in navs' name='{{nav.name}}' :style='{background:nav.color}'>{{nav.content}}</li>
       </ul>
     </div>
     <div class="day-hot middle">
       <span></span>
       <h6>每日推荐</h6>
     </div>
   </nav>
   <div class="main">
     <ul class="clearfix">
       <li v-for='pic in pics' @click='rec("dayRec")'>
         <img :src="pic.url">
         <p class='middle'>{{pic.content}}</p>
       </li>
     </ul>
   </div>
 </div>
</template>

<script>
import Search from 'components/search'
export default {
  data() {
    return {
      navs:[
        {color:'#d291be',content:'新品',name:'newPro'},
        {color:'#f096a7',content:'热销',name:'hotSell'},
        {color:'#94c9c8',content:'教程',name:'teach'},
        {color:'#9bcf9e',content:'问题',name:'question'},
      ],
      pics:[
      {url:require('../../images/star.jpg'),content:'唯美满天星'},
      {url:require('../../images/star.jpg'),content:'唯美满天星'},
      {url:require('../../images/star.jpg'),content:'唯美满天星'},
      {url:require('../../images/rose.jpg'),content:'永不凋谢的玫瑰'},
      {url:require('../../images/rose.jpg'),content:'永不凋谢的玫瑰'},
      {url:require('../../images/rose.jpg'),content:'永不凋谢的玫瑰'},
      ]
    }
  },
  components: {
    Search
  },
  ready(){
  },
  methods: {
    indexClick(event){
      this.indexview.preView[this.indexview.preView.length] = this.indexview.show
      this.indexview.show = event.currentTarget.getAttribute('name')
    },
    rec(view){
      this.indexview.preView[this.indexview.preView.length] = this.indexview.show
      this.indexview.show = view
    }
  },
  props:{
    mainshows:Object,
    indexview:Object,
  }  
}
</script>

<style scope>
.recommend{
  width: 100%;
  height: 28.0729vh;
  background: url(../../images/index01.jpg);
  background-size: 100%;
  text-align: center;
  position: relative;
  min-height: 210px;
}
.hot{
  width: 53.240%;
  height: 40.8163%;
  background: rgba(255,255,255,0.3);
  margin: auto;
  position: absolute;
  top: 20.5083%;
  left: 23.5%;
  min-width: 218px;
}
.hot p{
  height: 50%;
  width: 95%;
  margin-left: 2.5%;
  vertical-align: middle;
  font-size: 1.1em;
  color: white;
  min-width: 208px;
}
.hot p:first-of-type{
  border-bottom: 1px solid white;
}
nav{
  width: 100%;
  height: 19.7916vh;
  min-height: 152px;
}
nav .nav{
  height: 73.421%;
}
.nav ul{
  height: 100%;
  text-align: center;
}
.nav li{
  width: 15.925%;
  height: 15.925vw;
  float: left;
  border-radius: 50%;
  margin-left: 6.203%;
  margin-top: 4%;
  color: white;
  font-size: 1.4em;
}
.day-hot{
  height: 26.579%;
  padding-left: 4%;
}
.day-hot span{
  display: inline-block;
  vertical-align: middle;
  width: 4px;
  height: 78%;
  background: #f096a7;
}
.day-hot h6{
  display: inline-block;
  vertical-align: middle;
  font-size: 1.4em;
}
.main{
  width: 100%;
}
.main li{
  width: 48.5%;
  float: left;
  margin-left: 1%;
  margin-top: 1%;
  text-align: center;
  position: relative;
}
.main li img{
  width: 100%;
}
.main li p{
  position: absolute;
  width: 100%;
  background: rgba(0,0,0,0.5);
  bottom: 0;
  color: white;
  padding: 2px 0;
  font-size: 1.2em;
}
</style>





