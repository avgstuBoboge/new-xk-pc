<template>
  <div class="page-part">
    <el-card style="margin-right: auto;margin-left: auto;width: 80%">
      <span style="font-size: 18px">分院/年级/专业: </span>
      <el-cascader style="width: 30%;margin-left: 1%"
                   v-model="major"
                   :options="options"></el-cascader>
      <span style="font-size: 18px;margin-left: 1%">建议修读学期: </span>
      <el-select style="width: 10%;margin-left: 1%" v-model="semester">
        <el-option v-for="i in 10" :key="i" :label="i" :value="i"/>
      </el-select>
      <span style="font-size: 18px;margin-left: 1%">课程性质: </span>
      <el-select style="width: 18%;margin-left: 1%" v-model="category" clearable>
        <el-option label="必修" value="必修"/>
        <el-option label="限选" value="限选"/>
        <el-option label="公选" value="公选"/>
      </el-select>
      <el-button type="primary" style="float: right;width: 10%" icon="el-icon-search" round>查询</el-button>
    </el-card>
    <el-card style="margin-top:1%;margin-right: auto;margin-left: auto;width: 80%;height: 700px">
      <el-table :data="tableData" stripe max-height="650px">
        <el-table-column label="课程代码" align="center" prop="courseID" sortable/>
        <el-table-column label="课程名称" align="center" prop="courseName" width="300px" sortable/>
        <el-table-column label="学分" align="center" prop="credit" sortable/>
        <el-table-column label="周学时" align="center" prop="weekTime" sortable/>
        <el-table-column label="课程性质" align="center" prop="category" sortable/>
        <el-table-column label="专业方向" align="center" prop="direct" sortable/>
        <el-table-column label="是否短学期" align="center" prop="isShortTerm" sortable/>
      </el-table>
    </el-card>
  </div>
</template>

<script>
export default {
  name: "PlanPage",
  data() {
    return {
      major: '',
      semester: '',
      category: '',
      options: [
        {
          value: '计算机与科学学院',
          label: '计算机与科学学院',
          children: [
            {
              value: '2018',
              label: '2018',
              children: [{
                value: '计算机科学与技术',
                label: '计算机科学与技术'
              }, {
                value: '软件工程',
                label: '软件工程'
              }, {
                value: '统计学',
                label: '统计学'
              }, {
                value: '信息管理与信息系统',
                label: '信息管理与信息系统'
              }]
            }
          ]
        }
      ],
      tableData: [{
        courseID: '301396',
        courseName: '软件工程',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '必修',
        direct: '无方向',
        isShortTerm: ''
      }, {
        courseID: '401312',
        courseName: '电子商务概论',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '复合交叉组',
        isShortTerm: ''
      }, {
        courseID: 'B01075',
        courseName: '软件工程综合课程设计（二）',
        credit: '3.0',
        weekTime: '+3',
        category: '必修',
        direct: '无方向',
        isShortTerm: '是'
      }, {
        courseID: 'B01076',
        courseName: '软件体系结构原理与实践',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '必修',
        direct: '无方向',
        isShortTerm: ''
      }, {
        courseID: 'B01078',
        courseName: '人工智能导论',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '必修',
        direct: '无方向',
        isShortTerm: ''
      }, {
        courseID: 'B01080',
        courseName: '高级程序设计',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '软件系统开发方向',
        isShortTerm: ''
      }, {
        courseID: 'C01057',
        courseName: '智能终端与移动应用开发',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '移动互联网应用开发方向',
        isShortTerm: ''
      }, {
        courseID: 'C01061',
        courseName: '数学建模实用技术基础',
        credit: '2.0',
        weekTime: '+2',
        category: '限选',
        direct: '创新实践组',
        isShortTerm: '是'
      }, {
        courseID: 'C01100',
        courseName: '物联网技术与应用',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '移动互联网应用开发方向',
        isShortTerm: ''
      }, {
        courseID: 'C01104',
        courseName: '大数据技术概论',
        credit: '2.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '学科前沿组',
        isShortTerm: ''
      }, {
        courseID: 'C01129',
        courseName: '数据挖掘技术',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '大数据与人工智能方向',
        isShortTerm: ''
      }, {
        courseID: 'C01130',
        courseName: '创新训练(Ⅰ)',
        credit: '1.0',
        weekTime: '+1',
        category: '限选',
        direct: '创新实践组',
        isShortTerm: ''
      }, {
        courseID: 'C01139',
        courseName: '大数据可视化',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '学科前沿组',
        isShortTerm: ''
      }, {
        courseID: 'C01152',
        courseName: '软件过程管理原理与实践',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '拓展组',
        isShortTerm: ''
      }, {
        courseID: 'C01153',
        courseName: '深度学习应用开发',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '大数据与人工智能方向',
        isShortTerm: ''
      }, {
        courseID: 'C01156',
        courseName: '网络营销理论与实践',
        credit: '2.0',
        weekTime: '1.0-2.0',
        category: '限选',
        direct: '创业训练组',
        isShortTerm: ''
      }, {
        courseID: 'C01158',
        courseName: '用户体验设计',
        credit: '3.0',
        weekTime: '2.0-2.0',
        category: '限选',
        direct: '软件系统开发方向',
        isShortTerm: ''
      }, {
        courseID: 'F09001',
        courseName: '创新创业',
        credit: '2.0',
        weekTime: '2.0-0.0',
        category: '限选',
        direct: '无方向',
        isShortTerm: ''
      }]
    }
  }
}
</script>

<style scoped>

</style>