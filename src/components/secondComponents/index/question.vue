<template>
 <div class="question">
   <index-header-ques :text='name' :mainshows='mainshows' :indexview='indexview'></index-header-ques>
   <div v-for='info in datas'>
     <div class="question-top">
     <img :src="info.url">
     </div>
     <div class="question-bottom clearfix">
       <div class="question-user">
         <img :src="info.users">
         {{info.username}}
       </div>
       <div class="question-dec">
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
import indexHeaderQues from 'components/Header'
export default {
  data() {
    return {
      name:'常见问题',
      datas:[
        {
          url:require('./images/index (5).jpg'),
          users:require('./images/index (4).jpg'),
          username:"客服喵呜",
          title:'生如夏花干花店常见问题第十期',
          desc:'快递太暴力，花都碎了。。。怎么办',
          read:3235,
          star:4613,
          commend:1232
        },
        {
          url:require('./images/index (3).jpg'),
          users:require('./images/index (1).jpg'),
          username:"客服喵呜",
          title:'生如夏花干花店常见问题第九期',
          desc:'颜色不好看！！！',
          read:3235,
          star:4613,
          commend:1232
        }
      ]
    }
  },
  components: {
    indexHeaderQues
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
.question-top{
  width: 97%;
  margin: 1% auto;
  height: 55vw;
}
.question-top img{
  border-radius: 2%;
}
.question-user{
  float: left;
  width: 18%;
  height: 18vw;
  text-align: center;
  margin: 0 3.5% 0 3.5%;
  color: #858585;
  font-family: "微软雅黑";
}
.question-user img{
  border-radius: 50%;
  margin-top: -58%;
  position: relative;
}
.question-dec{
  float: left;
  width: 75%;
}
.question-dec h6{
  font-size: 1.15rem;
  padding: 0.3rem 0 0.1rem;
}
.question-dec p{
  font-size: 1rem;
  padding: 0.15rem 0;
}
.question-dec .data{
  float: right;
}.question-dec .data>span{
  padding: 0 0.8em;
  font-size: 0.9em;
  color: #bfbfbf;
}
</style>





