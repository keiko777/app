<template>
    <div>
        <el-header>
            <el-row>
                <el-col :span="24">
                <!--     <div class="grid-content bg-purple">
                        
                         <img src="../../assets/2k.jpeg"> 
                         <p>{{msg}}</p>
                        <img src="./assets/2k.jpeg"/>
                    </div>    
                </el-col>
                <el-col :span="12">
                    <div class="grid-content bg-purple-light">
                        <el-button type="primary">登录</el-button>
                        <el-button type="primary">注册</el-button>
                    </div> -->
                    <div class="navbar navbar-static-top bs-docs-nav" id="top">
                    <div class="container">
                        <div class="navbar-header">
                        <button class="navbar-toggle collapsed" type="button" data-toggle="collapse" data-target="#bs-navbar" aria-controls="bs-navbar" aria-expanded="false">
                            <span class="sr-only">Toggle navigation</span>
                            <span class="icon-bar"></span>
                            <span class="icon-bar"></span>
                            <span class="icon-bar"></span>
                        </button>
                        <a href="../" class="navbar-brand">{{msg}}</a>
                        </div>
                        <nav id="bs-navbar" class="collapse navbar-collapse">
                        <ul class="nav navbar-nav topButton el-col-18">
                            <li><el-button type="primary">注册</el-button></li>
                            <li><el-button type="primary">登录</el-button></li>
                        </ul>
                        </nav>
                    </div>
                    </div>
                </el-col>
            </el-row>
        </el-header>
    </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "2K18 build中文版"
    };
  }
};
</script>


