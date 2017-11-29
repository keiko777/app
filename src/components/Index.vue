<template>
  <div>
    <el-main>
      <!-- <p>{{msg}}</p> -->
        <div id="myCarousel" class="carousel slide" data-ride="carousel">
            <!-- 轮播（Carousel）指标 -->
            <ol class="carousel-indicators">
                <li data-target="#myCarousel" data-slide-to="0" class="active"></li>
                <li data-target="#myCarousel" data-slide-to="1"></li>
                <li data-target="#myCarousel" data-slide-to="2"></li>
            </ol>   
            <!-- 轮播（Carousel）项目 -->
            <div class="carousel-inner">
                <div class="item active">
                    <img src="../assets/1.jpg" alt="First slide">
                </div>
                <div class="item">
                    <img src="../assets/2.jpg" alt="Second slide">
                </div>
                <div class="item">
                    <img src="../assets/3.jpg" alt="Third slide">
                </div>
            </div>
            <!-- 轮播（Carousel）导航 -->
            <a class="carousel-control left" href="#myCarousel" 
                data-slide="prev">&lsaquo;
            </a>
            <a class="carousel-control right" href="#myCarousel" 
                data-slide="next">&rsaquo;
            </a>
        </div>
        <p>NBA 2K MyPlayer 模式模版</p>
            <el-row>
                 <el-col :span="2"> 
                     <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
            <ul class="grid-content bg-purple list">
                <li v-for="item in types">
                    {{item}}
                </li>
            </ul>
        </el-col>
                <el-col :span="6">
                    <div class="grid-content bg-purple">
                        <p>BUILD 1</p>
                        <Selection/>
                    </div>
                </el-col>
                <el-col :span="6">
                    <div class="grid-content bg-purple-light">
                        <p>BUILD 2</p>
                     <Selection/>
                    </div>
                </el-col>
                <el-col :span="6">
                    <div class="grid-content bg-purple">
                    <p>BUILD 3</p>
                    <Selection/>
                    </div>
                </el-col>
            </el-row>
            <div>
               
               
                
            </div>
    </el-main>
    <!-- <el-row :gutter="20">
        <el-col :span="2"> 
            <div class="grid-content bg-purple">
                <div v-for="item in types">
                    {{item}}
                </div>
            </div>
        </el-col>
    </el-row> -->
       
           
    <!-- <el-table
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="date"
        label="日期"
        width="180">
      </el-table-column>
      <el-table-column
        prop="name"
        label="姓名"
        width="180">
      </el-table-column>
      <el-table-column
        prop="address"
        label="地址">
      </el-table-column>
    </el-table> -->
 
  </div>
</template>

<script>    
import Selection from "../components/selection/Selection";
// import SelectionTest from '../components/selection/SelectionTest'
export default {
  data() {
    return {
      msg: "this is index page",
      types: [
        "_id",
        "acceleration",
        "athleticdunk",
        "ballhandling",
        "bigdunk",
        "blocks",
        "bronzebadge",
        "dribblemove",
        "dunks",
        "first",
        "goldbadge",
        "height",
        "hofbadge",
        "initial",
        "layups",
        "max",
        "midrange",
        "passing",
        "position",
        "postoffense",
        "quickness",
        "rebounding",
        "second",
        "silverbadge",
        "speed",
        "speedboost",
        "stamina",
        "steals",
        "strength",
        "three",
        "vertical"
      ]
    };
  },
  components: {
    Selection
    //   SelectionTest
  }
};
  $(function(){
    $('#myCarousel').carousel({
        interval: 7000
    });
});
</script>
