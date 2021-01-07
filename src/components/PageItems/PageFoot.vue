<template>
  <div class="page-foot">
    <p>
      <el-divider></el-divider>
      Copyright &copy; 2020-{{ new Date().getFullYear() }} Boboge. All Rights Reserved.<br>
      Powered by
      <el-link type="primary" href="https://github.com/avgstuBoboge">avgstuBoboge</el-link>
      &
      <el-link type="primary" href="https://github.com/PleasedSheep">PleasedSheep</el-link>
      &
      <el-link type="primary" href="https://github.com/b565310965">Scott</el-link>
    </p>
  </div>
</template>

<script>
export default {
  name: "PageFoot"
}
</script>

<style scoped>
.page-foot {
  background-color: rgba(247, 251, 253, 1);
  height: 120px;
  width: 100%;
  text-align: center;
}
</style>