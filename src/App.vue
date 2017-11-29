<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <router-view/> -->

  <Header/>
  <Index />
  <Footer/>

  </div>
</template>

<script>
import Header from './components/common/Header'
import Footer from './components/common/Footer'
import Index from './components/Index'
export default {
  name: 'app',
  data(){
    return{

    }
  },
  components:{
    Header,
    Index,
    Footer
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
ul li{
   list-style:none;
}
.list li{
  width:200px;
  height:35px;
  border-bottom:1px solid #999;
  border-left:1px solid #999;  
  border-right:1px solid #999;  
  line-height:35px;
}
.list:nth-child(0){
  border-top:1px solid #999;
}
.list{
  width:200px;
  margin:120px 0 0 53px;
}
.att{
  margin-top:60px;
  margin-left:100px;
}
.att li{
  border-bottom:1px solid #999;
  height:35px;
  line-height:35px;
}
.el-header{
  height:50px!important;
  padding:0;
  background:#f1f1f1;
}
.el-header a:hover{
  color:#66b1ff;
}
.topButton li{
  float:right;
  margin:5px 20px 0 0;
}
.el-footer{
  background-color: #2a2730;
  color:#fff;
  height:112px!important;
  padding:20px;
}
.item{
  width:100%;
  height:570px;
  background:pink;
}
.item img{
  width:100%;
  height:570px;
}
.el-main{ 
  width:100%;
  padding:0;
}
.navbar{
  margin-bottom:0;
  border:0;
}
</style>
