<template>
  <div class="page-part" style="min-height: 2800px">
    <div style="width: 8%;border: 1px solid;border-radius: 5px;margin-left: 2%;float: left">
      <div style="text-align:center;font-size:22px;color: #409EFF;margin-top: 10px"><i class="el-icon-more"/> 社区分类
      </div>
      <div style="text-align: center;color: gray;font-size: 10px">- - - - - - - - - - - - - - -</div>
      <el-menu class="el-menu-vertical-demo">
        <el-menu-item>
          <div class="nav-item"><i class="el-icon-s-comment"/>课程评价</div>
        </el-menu-item>
        <div style="text-align: center;color: gray;font-size: 10px">- - - - - - - - - - - - - - -</div>
        <el-menu-item>
          <div class="nav-item"><i class="el-icon-house"/>图书教室</div>
        </el-menu-item>
        <div style="text-align: center;color: gray;font-size: 10px">- - - - - - - - - - - - - - -</div>
        <el-menu-item>
          <div class="nav-item"><i class="el-icon-message"/>教务通知</div>
        </el-menu-item>
        <div style="text-align: center;color: gray;font-size: 10px">- - - - - - - - - - - - - - -</div>
        <el-menu-item>
          <div class="nav-item"><i class="el-icon-location-outline"/>校园设施</div>
        </el-menu-item>
        <div style="text-align: center;color: gray;font-size: 10px">- - - - - - - - - - - - - - -</div>
        <el-menu-item>
          <div class="nav-item"><i class="el-icon-thumb"/>代寄代拿</div>
        </el-menu-item>
        <div style="text-align: center;color: gray;font-size: 10px">- - - - - - - - - - - - - - -</div>
        <el-menu-item>
          <div class="nav-item"><i class="el-icon-watermelon"/>校园轶事</div>
        </el-menu-item>
        <div style="text-align: center;color: gray;font-size: 10px">- - - - - - - - - - - - - - -</div>
        <el-menu-item>
          <div class="nav-item"><i class="el-icon-s-grid"/>社区版务</div>
        </el-menu-item>
      </el-menu>
    </div>
    <div style="width: 80%;margin-left:3%;float: left">
      <div style="height: 450px">
        <el-card style="width: 50%;float: left">
          <el-carousel height="400px">
            <el-carousel-item v-for="item in 3" :key="item">
              <el-image :src="item + '.jpg'"/>
            </el-carousel-item>
          </el-carousel>
        </el-card>
        <el-card style="width: 40%;margin-left: 3%; float: left;height: 150px" shadow="hover">
          <el-button style="float: right;font-size: 22px" type="text"><i class="el-icon-more"/> 更多>></el-button>
          <div style="font-size: 22px">近期活动</div>
          <el-divider></el-divider>
          <div style="color: gray">近期暂无校园活动</div>
        </el-card>
        <el-card style="width: 40%;margin-left: 3%; margin-top: 30px; height:250px;float: left" shadow="hover">
          <div style="font-size: 22px">近期活跃社区</div>
          <el-divider></el-divider>
          <el-link style="font-size: 24px;float: left"><i style="color: gray" class="el-icon-thumb"/> 代寄代拿</el-link>
          <div style="font-size: 24px;float: left; margin-left: 10px;color: gray">近期发帖数:514</div>
          <div
              style="text-align: center;color: gray;font-size: 10px;float: left;margin-top: 10px;margin-bottom: 10px">
            -
            - - - - - - - - - - - - - - - - - -
            - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          </div>
          <el-link style="font-size: 24px;float: left"><i style="color: gray" class="el-icon-watermelon"/> 校园轶事
          </el-link>
          <div style="font-size: 24px;float: left; margin-left: 10px;color: gray">近期发帖数:114</div>
        </el-card>
      </div>
      <div style="width: 60%;float: left">
        <div style="font-size: 30px;margin-top: 20px;"><i class="el-icon-s-grid"/>热门帖子</div>
        <el-divider></el-divider>
        <div v-for="i in 10" v-bind:key="i" style="margin-top: 10px">
          <div style="height: 200px;border: 5px solid lightblue;border-radius: 10px">
            <el-image style="margin-left: 10px;height: 180px;width: 300px;float: left" class="vertical-center"
                      src="tiezi.jpg"></el-image>
            <el-link style="font-size: 24px;margin-top: 30px">目前对于大学生活的一些遗憾<br></el-link>
            <div style="float: right;font-size: 22px; color: gray"><br>校园轶事</div>
            <div style="float: right;font-size: 50px"><i class="el-icon-watermelon"/></div>
            <div style="font-size: 18px;"><br><br>PleasedSheep</div>
            <div style="font-size: 18px;color: lightgrey">22分钟前 <i class="el-icon-view"/>233</div>
            <div style="font-size: 18px;color: lightgrey"></div>
          </div>
        </div>
        <el-pagination
            :page-sizes="[10]"
            :page-size="100"
            layout="total, sizes, prev, pager, next, jumper"
            :total="400">
        </el-pagination>
      </div>
      <div style="width: 30%;margin-left: 5%;float: left">
        <div style="font-size: 30px;margin-top: 20px;"><i class="el-icon-rank"/>热帖排行</div>
        <el-divider/>
        <div v-for="i in 3" v-bind:key="i" style="height: 100px">
          <div style="background-color: red;border-radius: 50%;width: 50px;height: 50px;float: left">
            <div class="center" style="font-size: 30px; color: white;text-align: center">{{ i }}</div>
          </div>
          <div style="font-size: 18px;margin-top: 10px;margin-left: 10px;float: left">目前对于大学生活的一些遗憾</div>
          <div style="font-size: 14px;margin-top: 10px;margin-left: 10px;float: right;color: gray"> 校园轶事</div>
          <div style="float: right;font-size: 30px"><i class="el-icon-watermelon"/></div>
        </div>
        <div v-for="i in 7" v-bind:key="i" style="height: 100px">
          <div style="background-color: gray;border-radius: 50%;width: 50px;height: 50px;float: left">
            <div class="center" style="font-size: 30px; color: white;text-align: center">{{ 3 + i }}</div>
          </div>
          <div style="font-size: 18px;margin-top: 10px;margin-left: 10px;float: left">目前对于大学生活的一些遗憾</div>
          <div style="font-size: 14px;margin-top: 10px;margin-left: 10px;float: right;color: gray"> 校园轶事</div>
          <div style="float: right;font-size: 30px"><i class="el-icon-watermelon"/></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SocialPage"
}
</script>

<style scoped>
.nav-item {
  font-size: 20px;
  text-align: center;
}
</style>