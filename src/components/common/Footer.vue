<template>
     <div>
        <el-footer>
            <footer class="bs-docs-footer footer">
                <div class="container">
                    <p>{{msg}}</p>
                     <p>contact me :<br> by Email:{{email}}
                
                    </p>
                </div>
            </footer>
        </el-footer>
        
    </div>
</template>

<script>
export default {
    data(){
        return{
            msg:'@ian ',
            email:'zhangyanforwork@gmail.com'
        }
    }
}
</script>

<style>

</style>
