<template>
  <div class="page-part">
    <el-input placeholder="请输入课程名" v-model="kwords" class="input-with-select horizontal-center" style="width: 60%">
      <el-select v-model="yearInterval" slot="prepend" placeholder="所有学年" style="width: 150px"
                 clearable>
        <template v-for="i in 10">
          <el-option v-bind:key="i" :label="(nowYear-i+1).toString() + '-' + (nowYear-i+2).toString()"
                     :value="i"></el-option>
        </template>
      </el-select>
      <el-select v-model="semester" slot="prepend" placeholder="所有学期" style="width: 150px;margin-left: 10px"
                 clearable>
        <el-option label="1" value="1"></el-option>
        <el-option label="2" value="2"></el-option>
        <el-option label="3" value="3"></el-option>
      </el-select>
      <el-button slot="append" icon="el-icon-search"></el-button>
    </el-input>
    <el-card style="margin-right: auto;margin-left: auto;margin-top: 30px;width: 60%;height: 450px" shadow="never">
      <el-table style="margin: 0" :data="courseTableData"
                stripe="stripe" max-height="400">
        <el-table-column align="center" label="学年" prop="year" sortable></el-table-column>
        <el-table-column align="center" label="学期" prop="semester"></el-table-column>
        <el-table-column align="center" label="课程编号" prop="courseID" sortable></el-table-column>
        <el-table-column align="center" label="课程名称" prop="courseName" sortable></el-table-column>
        <el-table-column align="center" label="性质" prop="category" sortable></el-table-column>
        <el-table-column align="center" label="学分" prop="credit" sortable></el-table-column>
        <el-table-column align="center" label="成绩" prop="grade" sortable></el-table-column>
      </el-table>
    </el-card>
    <el-card style="margin-right: auto;margin-left: auto;margin-top: 30px;width: 60%;height: 300px" shadow="never">
      <el-table style="margin: 0" :data="creditTableData" stripe="stripe" max-height="250">
        <el-table-column align="center" label="课程性质" prop="category"></el-table-column>
        <el-table-column align="center" label="学分要求" prop="require"></el-table-column>
        <el-table-column align="center" label="获得学分" prop="gained"></el-table-column>
        <el-table-column align="center" label="未通过学分" prop="failed" width="300px"></el-table-column>
        <el-table-column align="center" label="还需学分" prop="need"></el-table-column>
      </el-table>
    </el-card>
    <div style="width: 60%;margin-left: auto;margin-right: auto;margin-top: 20px;font-size: 18px;">
      <span>平均学分绩点: {{ this.GPA }}</span>
      <span style="margin-left: 30px">学分绩点总和: {{ this.GPS }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "CreditPage",
  data() {
    return {
      kwords: '',
      yearInterval: '',
      semester: '',
      courseTableData: [{
        year: '2019-2020',
        semester: '2',
        courseID: '301259',
        courseName: '操作系统原理实验',
        category: '必修',
        credit: '1.0',
        grade: '优'
      }, {
        year: '2019-2020',
        semester: '2',
        courseID: 'C01106',
        courseName: 'ACM程序设计基础',
        category: '限选',
        credit: '2.0',
        grade: '95'
      }, {
        year: '2018-2019',
        semester: '2',
        courseID: '102147',
        courseName: '概率统计A',
        category: '必修',
        credit: '3.0',
        grade: '94'
      }, {
        year: '2019-2020',
        semester: '2',
        courseID: '109008',
        courseName: '中国近代史纲要',
        category: '必修',
        credit: '2.0',
        grade: '79'
      }, {
        year: '2020-2021',
        semester: '1',
        courseID: 'B01075',
        courseName: '软件工程综合课程设计(二)',
        category: '必修',
        credit: '3.0',
        grade: '优'
      }, {
        year: '2019-2020',
        semester: '1',
        courseID: 'B01074',
        courseName: '软件工程综合课程设计(一)',
        category: '必修',
        credit: '2.0',
        grade: '优'
      }, {
        year: '2019-2020',
        semester: '1',
        courseID: '025',
        courseName: '羽毛球5',
        category: '必修',
        credit: '1.0',
        grade: '80'
      }],

      creditTableData: [{
        category: '必修',
        require: '122',
        gained: '84',
        failed: '0',
        need: '38'
      }, {
        category: '限选',
        require: '31',
        gained: '14',
        failed: '0',
        need: '17'
      }, {
        category: '公选',
        require: '0',
        gained: '2',
        failed: '0',
        need: '0'
      }, {
        category: '合计',
        require: '165',
        gained: '100',
        failed: '0',
        need: '67'
      }],
      GPA: '4.7321',
      GPS: '473.2075',
      nowYear: new Date().getFullYear(),
    }
  }
}
</script>

<style scoped>

</style>