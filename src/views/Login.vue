<template>
  <div class="login-container">
    <div class="login-box">
      <!-- 头像区 -->
      <div class="avatar-box">
        <img src="../assets/logo.png"
             alt="">
      </div>
      <!--登录表单区-->
      <el-form ref="loginForm" :rules="rules" :model="loginForm" class="login-form">
        <el-form-item prop="username">
            <el-input placeholder="请输入用户名" v-model="loginForm.username">
              <i slot="prefix" class="iconfont icon-yonghu"></i>
            </el-input>
        </el-form-item>
        <el-form-item prop="password">
            <el-input placeholder="请输入密码" v-model="loginForm.password">
              <i slot="prefix" class="iconfont icon-suo"></i>
            </el-input>
        </el-form-item>
        <el-form-item class="btns">
          <el-button type="primary" @click="login">登录</el-button>
          <el-button type="info" @click="reset">重置</el-button>
        </el-form-item>
      </el-form>
      
      
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      loginForm: {
        username: '',
        password: ''
      },
      rules: {
        // 验证用户名是否合法
        username: [
          { required: true, message: '请输入用户名', trigger: 'blur'},
          { min: 3, max: 10, message: '用户名要求3-10个任意字符', trigger: 'blur' }
        ],
        // 验证密码是否合法
        password: [
          { required: true, message: '请输入密码', trigger: 'blur'},
          { min: 6, max: 15, message: '密码要求6-15个任意字符', trigger: 'blur' }
        ]
      }
     
    }
  },
  methods: {
    login(){
      this.$message({message: 'aaaaaaaaaa', type: 'success'})
      this.$refs['loginForm'].validate( valid => {
        if(valid){
          console.log('submit ok')
        }
      })
    },
    reset(){
      this.$refs['loginForm'].resetFields()
    }
  }
}
</script>

<style lang="scss" scoped>
.login-container {
  background: #2b4b6b;
  height: 100%;
}
.login-box {
  background: #fff;
  width: 450px;
  height: 300px;
  border-radius: 5px;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  .avatar-box {
    height: 130px;
    width: 130px;
    border: 1px solid #eee;
    padding: 10px;
    border-radius: 50%;
    box-shadow: 0 0 10px #ddd;
    position: absolute;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #fff;
    img {
      height: 100%;
      width: 100%;
      border-radius: 50%;
      background-color: #eee;
    }
  }
}

.login-form{
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 0 20px;
  box-sizing: border-box;
  .btns{
    display: flex;
    justify-content: flex-end;
  }
}
</style>