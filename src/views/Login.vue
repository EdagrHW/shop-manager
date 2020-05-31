<template>
  <div class="login-container">
    <div class="login-box">
      <!-- 头像区 -->
      <div class="avatar-box">
        <img src="../assets/logo.png"
             alt="">
      </div>
      <!--登录表单区-->
      <el-form model="login" class="login-form">
        <el-form-item>
            <el-input placeholder="请输入用户名" v-model="login.username">
              <i slot="prefix" class="iconfont icon-yonghu"></i>
            </el-input>
        </el-form-item>
        <el-form-item>
            <el-input placeholder="请输入密码" v-model="login.password">
              <i slot="prefix" class="iconfont icon-suo"></i>
            </el-input>
        </el-form-item>
        <el-form-item class="btns">
          <el-button type="primary">登录</el-button>
          <el-button type="info">重置</el-button>
        </el-form-item>
      </el-form>
      
      
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      login: {
        username: '',
        password: ''
      }
     
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