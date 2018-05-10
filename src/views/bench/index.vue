<template>
  <div id="bench">
    <panel-group></panel-group>
    <div style="border-top:1px solid #e6e6e6;padding: 10px">
      <svg-icon icon-class="user"/>
      <span>快速入口</span>
    </div>
    <div style="display: flex;border-top:1px solid #e6e6e6;padding: 10px;text-align: center">
      <div style="flex: 1;margin: 10px;background-color:#999;height: 60px;line-height: 60px">
        <svg-icon icon-class="user"/>
        <span>会员充值</span>
      </div>
      <div style="flex: 1;margin: 10px;background-color:#999;height: 60px;line-height: 60px">
        <svg-icon icon-class="user"/>
        <span>新增会员</span>
      </div>
      <div style="flex: 1;margin: 10px;background-color:#999;height: 60px;line-height: 60px">
        <svg-icon icon-class="user"/>
        <span>开单</span>
      </div>
    </div>
    <div style="border-top:1px solid #e6e6e6;padding: 10px">
      <svg-icon icon-class="user"/>
      <span>最新订单</span>
    </div>
    <div style="border-top:1px solid #e6e6e6;padding: 10px">
      <el-table
        :data="tableData"
        style="width: 100%">
        <el-table-column
          prop="date"
          label="日期">
        </el-table-column>
        <el-table-column
          prop="name"
          label="姓名">
        </el-table-column>
        <el-table-column
          prop="address"
          label="消费时间">
        </el-table-column>
      </el-table>
    </div>
  </div>
</template>

<script>
import PanelGroup from './components/PanelGroup'
export default {
  components: {
    PanelGroup
  },
  data () {
    return {
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }]
    }
  }
}
</script>

<style rel="stylesheet/scss" lang="scss">
#bech {

}
</style>
