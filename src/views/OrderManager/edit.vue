<template>
  <div class="createPost-container">
    <sticky :className="'sub-navbar publish'">
      <el-button type="warning" @click="goBack()">返回</el-button>
    </sticky>
    <el-tabs>
      <el-tab-pane label="订单详情">
        <order-detail-pane :order-id="orderId"></order-detail-pane>
      </el-tab-pane>
      <el-tab-pane label="物流信息">
      </el-tab-pane>
      <el-tab-pane label="操作日志">
      </el-tab-pane>
    </el-tabs>
  </div>
</template>
<script>
import Sticky from '../../components/Sticky'
import OrderDetailPane from './orderDetailPane.vue'
export default {
  name: 'EditOrder',
  components: {
    Sticky,
    OrderDetailPane
  },
  data () {
    return {
    }
  }
}

</script>
<style ref="stylesheet/scss" lang="scss">

</style>
