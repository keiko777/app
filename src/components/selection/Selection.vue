<template>
    <div>
    
        <p>位置</p>
        <!-- <el-select @visible-change="choosePosition(po)" v-model="po" clearable placeholder="请选择">
            <el-option v-for="item in position" :key="item.value" :label="item.label" :value="item.label">
            </el-option>
        </el-select> -->
        <el-select v-model="po" clearable placeholder="请选择">
            <el-option v-for="position in positions" :key="position.value" :label="position.label" :value="position.label">
            </el-option>
        </el-select>
        <p>主技能</p>
        <el-select v-model="first" clearable placeholder="请选择">
            <el-option v-for="item in chooseFirst" :key="item" :label="item" :value="item">
            </el-option>
        </el-select>
        <p>副技能</p>
         <el-select  v-model="second" clearable placeholder="请选择">
            <el-option v-for="item in chooseSecond" :key="item" :label="item" :value="item">
            </el-option>
        </el-select>
        <p>身高</p>
        <el-select v-model="height" clearable placeholder="请选择">
            <el-option v-for="item in chooseHeight" :key="item" :label="item" :value="item">
            </el-option>
        </el-select><br><br>
        <el-button type="primary" @click="finish(po,first,second,height)">确定</el-button>
        <ul class="att">
          <li v-for="item in att">
          {{item}}
          </li>
        </ul>
    </div>
</template>

<script>
// import axios from "axios";
import Table from "../table/Table";
export default {
  data() {
    return {
      positions: [
        {
          value: "选项1",
          label: "控球后卫/PG",
          firstSkills: ["三分球", "专注防守", "冲击篮筐", "组织核心", "运球投篮"],
          heights: [
            "5'7",
            "5'8",
            "5'9",
            "5'10",
            "5'11",
            "6'0",
            "6'1",
            "6'2",
            "6'3",
            "6'4",
            "6'5",
            "6'6",
            "6'7"
          ],
          secondSkills: ["三分球", "专注防守", "冲击篮筐", "组织核心", "背身得分", "篮板猛兽", "运球投篮"]
        },
        {
          value: "选项2",
          label: "得分后卫/SG",
          firstSkills: ["三分球", "专注防守", "冲击篮筐", "组织核心", "运球投篮"],
          heights: [
            "5'10",
            "5'11",
            "6'0",
            "6'1",
            "6'2",
            "6'3",
            "6'4",
            "6'5",
            "6'6",
            "6'7",
            "6'8"
          ],
          secondSkills: ["三分球", "专注防守", "冲击篮筐", "组织核心", "背身得分", "篮板猛兽", "运球投篮"]
        },
        {
          value: "选项3",
          label: "小前锋/SF",
          firstSkills: ["三分球", "专注防守", "冲击篮筐", "组织核心", "运球投篮", "背身得分", "篮板猛兽"],
          heights: ["6'3", "6'4", "6'5", "6'6", "6'7", "6'8", "6'9", "6'10"],
          secondSkills: ["三分球", "专注防守", "冲击篮筐", "组织核心", "背身得分", "篮板猛兽", "运球投篮"]
        },
        {
          value: "选项4",
          label: "大前锋/PF",
          firstSkills: ["三分球", "专注防守", "冲击篮筐", "背身得分", "篮板猛兽"],
          heights: ["6'5", "6'6", "6'7", "6'8", "6'9", "6'10", "6'11", "7'0"],
          secondSkills: ["三分球", "专注防守", "冲击篮筐", "组织核心", "背身得分", "篮板猛兽", "运球投篮"]
        },
        {
          value: "选项5",
          label: "中锋/C",
          firstSkills: ["三分球", "专注防守", "冲击篮筐", "背身得分", "篮板猛兽"],
          heights: ["6'8", "6'9", "6'10", "6'11", "7'0", "7'1", "7'2", "7'3"],
          secondSkills: ["三分球", "专注防守", "冲击篮筐", "组织核心", "背身得分", "篮板猛兽", "运球投篮"]
        }
      ],

      po: "",
      first: "",
      second: "",
      height: "",
      types: [],
      att: []
    };
  },

  computed: {
    chooseFirst: function() {
      for (var i = 0; i < this.positions.length; i++) {
        if (this.positions[i].label === this.po) {
          // console.log(this.positions[i].firstSkills);
          return this.positions[i].firstSkills;
        }
      }
    },
    chooseSecond: function() {
      for (var i = 0; i < this.positions.length; i++) {
        if (this.positions[i].label === this.po) {
          // console.log(this.positions[i].secondSkills);
          return this.positions[i].secondSkills;
        }
      }
    },
    chooseHeight: function() {
      for (var i = 0; i < this.positions.length; i++) {
        if (this.positions[i].label === this.po) {
          // console.log(this.positions[i].heights);
          return this.positions[i].heights;
        }
      }
    }
    // chooser: function(){
    //     for (var i = 0; i < this.positions.length; i++) {
    //                 if (this.positions[i].label === this.po) {
    //                     var result = []
    //                     result.push(this.positions[i].heights)
    //                     result.push(this.positions[i].secondSkills)
    //                     result.push(this.positions[i].firstSkills)
    //                     return result;
    //                 }
    //             }
    // }
  },
  methods: {
    finish(po, first, second, height) {
      // var jsonp = require("jsonp");
      var req = {
        position: this.po,
        first: this.first,
        second: this.second,
        height: this.height
      };
      // console.log(req);
      var self = this;
      console.log(req)
      self.$http.post("http://192.168.178.202:8081/build", req).then(response => {
        if (response.status == 200) {
          console.log(response);
          var body = response.body;
          for (var i in body) {
            if (Object.prototype.hasOwnProperty.call(body, i)) {
              //过滤
              this.types.push(i);
              this.att.push(body[i]);
            }
          }
        }
        if (this.arr != null) {
          console.log(this.att);
        }
      });

      // jsonp("http://api.douban.com/v2/movie/top250",null, function(err, data) {
      //   if (err) {
      //     console.error(err.message);
      //   } else {
      //     console.log(data);
      //   }
      // });

      // axios.get("http://api.douban.com/v2/movie/top250", {
      //     })
      //   .then(function(response) {
      //     console.log(response);
      //   })
      //   .catch(function(error) {
      //     console.log(error);
      //   });
    }
  }
};
</script>

<style>

</style>
