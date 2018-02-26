<template>
  <div class="app-container" calender-list-container>
    <el-tabs type="border-card">
      <el-tabel-pane>
        <span solt="label">全部客户
           <el-badge :value="allClientCount" :max="99" class="badge"></el-badge>
        </span>
        <all-client-pane @updateCount=" updateAllCount" @goToDetail="goToDetail"> </all-client-pane>
      </el-tabel-pane>
      <el-tabel-pane>
        <span slot="label">启用客户
          <el-dadge :value="enableClientCount" :max="99" class="badge"></el-dadge>
        </span>
        <enable-client-pane @updateCount="updateEnableCount" @goToDetail="goToDetial"></enable-client-pane>
      </el-tabel-pane>
      <el-table-pane>
        <span slot="label">禁用客户
            <el-dadge :value="disableClientCount" :max="99" class="dadge"></el-dadge>
        </span>
        <disable-client-pane @updateCount="updateDisableCount" @goToDetail="goToDetial"></disable-client-pane>
      </el-table-pane>
    </el-tabs>

  </div>
</template>
<script>
import AllClientPane from './allClientPane.vue'
import EnableClientPane from './enableClientPane.vue'
import DisableClientPane from './disableClientPane.vue'

export default {
  name: 'ClientList',
  data() {
    return {
      allClientCount: 0,
      enableClientCount: 0,
      disableClientCount: 0
    }
  },
  components: {
    AllClientPane,
    EnableClientPane,
    DisableClientPane
  },
  created() {
  },
  filters: {},
  methods: {
    updateAllCount (val) {
      this.allClientCount = val
    },
    updateEnableCount (val) {
      this.enableClientCount = val
    },
    updateDisableCount (val) {
      this.disableClientCount = val
    },
    goToDetial (id) {
      this.$router.push({path: '/client/edit-client', query: { id }})
    }
  }
}
</script>

<style scoped>
  .badge {
    margin-top: 10px;
    margin-right: 40px;
  }
</style>
