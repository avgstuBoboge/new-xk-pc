<template>
  <div>
    <div class="menu" style="background-color: #1976d2">
      <img src="../../assets/logo.png" style="width: 58px; height: 58px;float: left" class="vertical-center"/>
      <div class="vertical-center" style="margin-left: 20px;font-size: 30px;color: white;float: left">教务辅助系统</div>
      <div class="user-box vertical-center">
        <template v-if="this.$store.state.user.username">
          <UserBox></UserBox>
        </template>
      </div>
    </div>
    <el-menu
        :default-active="this.$route.path"
        class="menu"
        mode="horizontal"
        background-color="#2196f3"
        text-color="#fff"
        active-text-color="#bdbdbd"
        style="border-radius:0 0 10px 10px;"
        router>
      <el-menu-item index="/" class="menu-item" route="/">首 页</el-menu-item>
      <template v-if="this.$store.state.user.username" class="menu-item">
        <el-menu-item index="/main" route="/main" class="menu-item">选 课</el-menu-item>
        <el-menu-item index="/credit" route="/credit" class="menu-item">已修课程查询</el-menu-item>
        <el-menu-item index="/plan" route="/plan" class="menu-item">培养计划</el-menu-item>
        <el-menu-item index="/social" route="/social" class="menu-item">社区</el-menu-item>
      </template>
    </el-menu>
  </div>
</template>

<script>
import UserBox from "@/components/PageItems/UserBox";

export default {
  name: "page-nav",
  components: {UserBox},
  data() {
    return {
      activeIndex: '1',
      login: false,
      username: 'test',
      fit: 'fill'
    };
  }
}
</script>

<style scoped>
.menu-item {
  font-size: 18px;
  text-align: center;
  width: 18%;
}

.menu {
  width: 90%;
  height: 60px;
  margin-right: auto;
  margin-left: auto;
  padding-left: 5%;
}

.user-box {
  height: 60px;
  float: right;
  margin-right: 20px;
  font-size: 18px;
}
</style>