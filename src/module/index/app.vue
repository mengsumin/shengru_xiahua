<template>
  <div class="container">
   <component :shows='currentView' :is="currentView.show" transition="fade" transition-mode="out-in" keep-alive>
   </component>
  </div>
</template>
<script>
import index from 'components/index'
import classify from 'components/classify'
import buy from 'components/buy'
import user from 'components/user'
export default {
  data() {
    return {
      currentView: {show:'user',checked:0,preView:[],preChecked:[]},
    }
  },
  components: {
    classify,
    index,
    buy,
    user
  },
  ready(){
  },
  methods: {
  }  
}
</script>

<style>
body {
  font-family:"\5b8b\4f53";
  background: #fff
}
a,
address,
b,
big,
blockquote,
body,
center,
cite,
code,
dd,
del,
div,
dl,
dt,
em,
fieldset,
font,
form,
h1,
h2,
h3,
h4,
h5,
h6,
html,
i,
iframe,
img,
ins,
label,
legend,
li,
ol,
p,
pre,
small,
span,
strong,
u,
ul,
var {
  margin: 0;
  padding: 0
}

article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
nav,
section,
summary {
  display: block
}

hr{
  -moz-box-sizing: content-box;
  box-sizing: content-box;
  height: 0
}

button,
html input[type=button],
input[type=submit] {
  -webkit-apperance: button;
  cursor: pointer
}

button[disabled],
html input[disabled] {
  cursor: default
}
ol,
ul {
  list-style: none
}

.container{
  width: 100%;
  height: 100vh;
}
.clearfix::after{
  clear:both;
  content: '';
  display: block;
  visibility: hidden;
  height: 0;
}
.middle::after{ 
  content: '';
  height: 100%;
  overflow: hidden;
  display: inline-block;
  vertical-align: middle;
}
img{
  width: 100%;
  height: 100%;
}
.left{
  float: left;
}
.right{
  float: right;
}
</style>





