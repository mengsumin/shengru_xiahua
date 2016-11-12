<template>
   <div class="wel">
     <ul @touchstart='startslider' @touchmove='moveslider' @touchend='endslider' @mouseup='slider'>
       <li class="slider" v-for='pic in pics'><img :src="pic"></li>
     </ul>
   </div>
</template>

<script>
import $ from 'jquery'
export default {
  data() {
    return {
      pics:[
        require('../../assets/images/yindao_01.png'),
        require('../../assets/images/yindao_02.jpg'),
        require('../../assets/images/yindao_03.jpg'),
        require('../../assets/images/yindao_04.jpg')
      ],
      flag:{
        index:0,//标记当前滑动位置
        startX:0,//标记第一次触摸位置
        current:0,//当前随滑动而改变的位置
        account:4//滑动的图片数量
      }
    }
  },
  components: {
  },
  ready(){
    
  },
  methods: {
    startslider(event){
      let touch = event.touches[0] 
      this.flag.startX = touch.pageX
      this.flag.current = Number.parseInt($(this.$el).find('ul').css('left'))
    },
    moveslider(event){
      let touch = event.touches[0] //获取第一个触点  
      let x = Number(touch.pageX) //页面触点X坐标  
      this.flag.screenWidth = Number.parseInt(screen.width);//屏幕宽度
      if(x - this.flag.startX<0&&x - this.flag.startX>-400){
        if(this.flag.current>-(this.flag.account-1)*this.flag.screenWidth){
          $(this.$el).find('ul').css({'left': (this.flag.current + x - this.flag.startX)})
        }else{
          window.location.href = "index.html"
        }
      }
    },
    endslider(event){
      let left = Number.parseInt($(this.$el).find('ul').css('left'))
      if(this.flag.current != left){
        this.flag.index++
        $(this.$el).find('ul').animate({'left': -this.flag.screenWidth*this.flag.index},100)
      }
    },
    slider(){
      try {  
          document.createEvent("TouchEvent");
        }
      catch (e) {  
         //如果是非移动设备，不支持滑动事件，改为点击事件
         this.flag.index++
         this.flag.index==this.flag.account?window.location.href = "index.html":''
         $(this.$el).find('ul').animate({'left': -450*this.flag.index},700)
      } 
    }
  }  
}
</script>
<style scope>
  ul,li{
    margin: 0;
    padding: 0;
  }
  .wel{
    width: 100%;
    height: 100vh;
    position: relative;
    overflow: hidden;
  }
  .wel ul{
    width: 400%;
    position: absolute;
    left: 0;
  }
 
  @media screen and (min-width: 960px){
    body{
      background-color: #deead8;
    }
    .wel{
      width: 450px;
      margin: auto;
    }
  }
  .wel ul li{
    width: 25%;
    list-style: none;
    float: left;
    overflow: hidden;
  }
  .wel ul li>img{
    width: 100%;
    height: 100%;
  }
</style>





