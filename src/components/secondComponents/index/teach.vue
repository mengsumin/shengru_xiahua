<template>
 <div class="teach">
   <index-header-rec :text='name' :mainshows='mainshows' :indexview='indexview'></index-header-rec>
   <div v-for='info in datas'>
     <div class="teach-top">
     <img :src="info.url" @click='go("teachDetail")'>
     </div>
     <div class="teach-bottom clearfix">
       <div class="teach-user">
         <img :src="info.users">
         {{info.username}}
       </div>
       <div class="teach-dec">
         <h6>{{info.title}}</h6>
         <p>{{info.desc}}</p>
         <div class="data">
           <span><span>{{info.read}}</span>阅读</span>
           <span><span>{{info.star}}</span>收藏</span>
           <span><span>{{info.commend}}</span>评论</span>
         </div>
       </div>
     </div>
   </div>
 </div>
</template>

<script>
import indexHeaderRec from 'components/Header'
export default {
  data() {
    return {
      name:'干花教程',
      datas:[
        {
          url:require('./images/index (1).jpg'),
          users:require('./images/index (3).jpg'),
          username:"生如夏花",
          title:'生如夏花干花店干花教程第十期',
          desc:'教你如何制作美丽的书签干花',
          read:3235,
          star:4613,
          commend:1232
        },
        {
          url:require('./images/index (2).jpg'),
          users:require('./images/index (5).jpg'),
          username:"生如夏花",
          title:'生如夏花干花店干花教程第九期',
          desc:'教你如何制作美丽的书签干花',
          read:3235,
          star:4613,
          commend:1232
        }
      ]
    }
  },
  components: {
    indexHeaderRec
  },
  ready(){
  },
  methods: {
    go(view){
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
.teach-top{
  width: 97%;
  margin: 1% auto;
  height: 55vw;
}
.teach-top img{
  border-radius: 2%;
}
.teach-user{
  float: left;
  width: 18%;
  height: 18vw;
  text-align: center;
  margin: 0 3.5% 0 3.5%;
  color: #858585;
  font-family: "微软雅黑";
}
.teach-user img{
  border-radius: 50%;
  margin-top: -58%;
  position: relative;
}
.teach-dec{
  float: left;
  width: 75%;
}
.teach-dec h6{
  font-size: 1.15rem;
  padding: 0.3rem 0 0.1rem;
}
.teach-dec p{
  font-size: 1rem;
  padding: 0.15rem 0;
}
.teach-dec .data{
  float: right;
}.teach-dec .data>span{
  padding: 0 0.8em;
  font-size: 0.9em;
  color: #bfbfbf;
}
</style>





