<template>
  <el-container class="home-container">
    <!--头部区域-->
    <el-header>
      <div>
        <img src="../assets/logo.png"
             alt="">
        <span>电商后台管理系统</span>
      </div>
      <el-button type="info">退出</el-button>
    </el-header>
    <el-container>
      <!--侧边栏-->
      <el-aside :width="collapse ? '64px' : '200px'">
        <div class="toggle-button" @click="toggleCollapse">|||</div>
       <!--侧边菜单栏-->
        <el-menu background-color="#333744"
                 text-color="#fff"
                 active-text-color="#409eff"
                 :unique-opened="true"
                 :collapse="collapse"
                 :collapse-transition="false">
          <!--一级菜单-->
          <el-submenu :index="item.id + ''" v-for="item in menulist" :key="item.id">
            <!--一级菜单的模板区域-->
            <template slot="title">
              <i :class="iconsObj[item.id]"></i>
              <!--文本-->
              <span>{{item.authName}}</span>
            </template>
            <!--二级菜单-->
            <el-menu-item :index="subItem.id + ''" v-for="subItem in item.children" :key="subItem.id">
              <template slot="title">
                <i :class="iconsObj[subItem.id]"></i>
                <!--文本-->
                <span>{{subItem.authName}}</span>
              </template>
            </el-menu-item>
          </el-submenu>

        </el-menu>
      </el-aside>
      <el-container>
        <el-main>Main</el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </el-container>
  </el-container>
</template>

<script>
export default {
  data (){
    return {
      menulist: [
        {
          id: 101,
          authName: '商品管理',
          path: null,
          children: [
            {
              id: 104,
              authName: '商品列表',
              path: null,
              children: []
            }
          ]
        }
      ],
      iconsObj: {
        '101': 'iconfont icon-suo',
        '104': 'iconfont icon-suo'
      },
      collapse: false
    }
  },
  methods: {
    // 点击按钮切换菜单的折叠和展开
    toggleCollapse () {
      this.collapse = !this.collapse
    }
  }
}
</script>

<style lang="scss" scoped>
.home-container {
  height: 100%;
}
.el-header {
  background-color: #373d41;
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #fff;
  font-size: 20px;
  padding-left: 0px;
  div {
    display: flex;
    align-items: center;
    img {
      height: 30px;
      width: 30px;
    }
    span {
      margin-left: 10px;
    }
  }
}
.el-aside {
  background-color: #333744;
  .el-menu{
    border-right: none;
  }
  .toggle-button{
    background-color: #4a5064;
    color: #fff;
    font-size: 10px;
    line-height: 20px;
    text-align: center;
    letter-spacing: 0.2em;
  }
  .toggle-button:hover{
    cursor: pointer;
  }
}
.el-main {
  background-color: #eaedf1;
}
.el-footer {
  background-color: #ccc;
}
.iconfont{
  margin-right: 10px;
}
</style>