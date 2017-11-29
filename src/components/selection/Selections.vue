<template>
    <div>
       
        <p>位置</p>
        <el-select v-model="position" placeholder="请选择">
            <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.label" @select="choosePosition">
            </el-option>
         </el-select>
    </div>
</template>

<script>
export default {
  data() {
    return {
      options: [
        {
          value: "选项1",
          label: "控球后卫/PG"
        },
        {
          value: "选项2",
          label: "得分后卫/SG"
        },
        {
          value: "选项3",
          label: "小前锋/SF"
        },
        {
          value: "选项4",
          label: "大前锋/PF"
        },
        {
          value: "选项5",
          label: "中锋/C"
        }
      ],
      position: ""
    };
  }, 
//   computed:{
//       options:function(){
//           alert(this.data.position)
//       }
//   },
  methods:{
      choosePosition(){
          alert(this.data.position)
      }
  }
};
</script>

<style>

</style>
