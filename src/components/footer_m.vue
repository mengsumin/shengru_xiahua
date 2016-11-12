<template>
  <div class='foot'>
    <footer>
      <ul class="clearfix">
        <li v-for='icon in icons' @click='change'>
          <img class="black"  :src='icon.urlchecked' v-if='$index==shows.checked'></img>
          <img class="red"  :src='icon.url' v-else></img>
          <p :class='$index==shows.checked?"actived":""'>{{icon.body}}</p>
        </li>
      </ul>
    </footer>
  </div>
</template>
<script>
import $ from 'jquery'
  export default{
    data(){
      return {
        icons:[
          {
            name:'index',
            url:require("../assets/images/icon23_01.jpg"),
            urlchecked:require("../assets/images/icon23_02.jpg"),
            body:'首页'
          },
          {
            name:'classify',
            url:require("../assets/images/icon23_011.jpg"),
            urlchecked:require("../assets/images/icon23_03.jpg"),
            body:'分类'
          },
          {
            name:'buy',
            url:require("../assets/images/icon23_06.jpg"),
            urlchecked:require("../assets/images/icon23_07.jpg"),
            body:'购物车'
          },
          {
            name:'user',
            url:require("../assets/images/icon23_09.jpg"),
            urlchecked:require("../assets/images/icon23_10.jpg"),
            body:'我'
          },
        ]
      }
    },
    props:{
      shows:Object,
      indexview:Object
    },
    methods:{
      change(){
        this.shows.preView[this.shows.preView.length] = this.shows.show
        this.shows.preChecked[this.shows.preChecked.length] = this.shows.checked
        this.indexview.show = this.icons[this.shows.checked].name+'Main'
        this.indexview.preView = []
        let curr = $(event.currentTarget).index()
        this.shows.checked = curr
        this.shows.show = this.icons[curr].name
      }
    },
    ready(){
    }
  }
</script>
<style scope>
  .foot{
    height: 8.6041vh;
    min-height: 60px;
  }
  .foot footer{
    width: 100%;
    height: 8.6041vh;
    min-height: 60px;
    position: fixed;
    border-top: 1px solid rgba(0,0,0,0.8);
    bottom: 0;
    background-color: white;
  }
  .foot footer ul{
    height: 100%;
  }
  .foot footer li{
    width: 24%; 
    height: 100%;
    float: left;
    margin: 0;
    padding-top: 1%;
    text-align: center;
  }
  .foot footer li p{
    height: 30%;
    padding-bottom: 1%;
  }
  .foot footer li img{
    height:55%;
    width: auto;
  }
  .foot footer li:last-of-type img.red{
    position: relative;
    left: 1%;
  }
  .foot footer li:last-of-type img.black,.foot footer li:nth-of-type(3) img.black{
    position: relative;
    left: 1.3%;
  }
  .foot footer li:last-of-type img.black{
    left: 3%;
  }
  p.actived{
    color: #f096a7;
  }
</style>