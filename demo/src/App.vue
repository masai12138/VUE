<template>
  <div id="app">
    <div class="top">
      <div class="title-span" style="cursor:pointer">
        {{title}}
        </div>
      <div class="bar" style="cursor:pointer">
        <a class="zong">{{zong}}</a>
        <a class="jian">{{jian}}</a>
        <a class="te" >{{te}}</a>
        <a class="about" v-on:click="about1()">{{about}}</a>
      </div>
    </div>
     <HelloWorld></HelloWorld>
  </div>
   
</template>

<style>
*{
  margin:0; 
  padding:0;
  }
#app{
  overflow: hidden;
  width: 100%;
  height: 100%;

}
.top{
  /* position :absolute; */
  width: 100%;
  height: 50px;
  background-color :dimgrey;
  
}
.title-span{
  float: left;
  height: 100%;
  width: 150px;
  /* padding-top: 10px; */
  margin-left: 200px;
  color: beige;
  font-size: 18px;
  text-align: center;
  line-height:50px;
}
.title-span:hover{
  color: aliceblue;
}
.bar{
  float: left;
  width: 200px;
  height: 100%;
  margin-left: 10px;
  line-height:50px;
  color: beige;
  font-size: 16px;
}
.zong:hover{
  color: aliceblue;
}
.te:hover{
  color: aliceblue;
}
.jian:hover{
  color: aliceblue;
}
.about:hover{
  color: aliceblue;
}
.zong{
  margin-left: 10px;
}
.te{
  margin-left:10px;
}
.jian{
  margin-left: 10px;
}
.about{
  margin-left: 10px;
}




</style>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  data :function(){
    return{
      title : '现代浏览器博物馆',
      zong : '综合 ',
      jian : '简介',
      te : '特点',
      about : '关于',
    }
  },
  methods :{
    about1 : function(){
      alert("这是由aimyon后援会出品的粉丝网站");
      
    }
  },
  components: {
    HelloWorld
  }
}
</script>

