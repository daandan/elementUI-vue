<template>
  <div>
    <template v-for="item in routes">
      <!--<router-link v-if="!item.hidden&&item.noDropdown&&item.children.length>0" :to="item.path+'/'+item.children[0].path">-->
        <!--<el-menu-item :index="item.path+'/'+item.children[0].path" @click="stateDrop(item.noDropdown)">-->
          <!--<i v-if='item.icon' class="item-icon fa fa-fw" aria-hidden="true" :class="item.icon"></i>{{item.name}}-->
        <!--</el-menu-item>-->
      <!--</router-link>-->
      <el-submenu :index="item.name" v-if="item.noDropdown&&!item.hidden" @click="stateDrop(item.noDropdown)">
        <template slot="title">
          <router-link  :to="item.path+'/'+item.children[0].path">
          <i v-if='item.icon' class="fa item-icon fa-fw" aria-hidden="true" :class="item.icon"></i>{{item.name}}
          </router-link>
        </template>
        <template v-for="child in item.children" v-if='!child.hidden'>
          <sidebar-item class='menu-indent' v-if='child.children&&child.children.length>0' :routes='[child]'> </sidebar-item>
          <router-link v-else class="menu-indent" :to="item.path+'/'+child.path">
            <el-menu-item :index="item.path+'/'+child.path">
              {{child.name}}
            </el-menu-item>
          </router-link>
        </template>
      </el-submenu>
    </template>
  </div>
</template>

<script>
export default {
  name: 'SidebarItem',
  props: {
    routes: {
      type: Array
    }
  },
  methods:{
    stateDrop(attr) {
      attr = !attr
      alert(attr)
    }
  },
  mounted(){

  }
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
  .item-icon {
    margin-right: 15px;
  }

  .hideSidebar .menu-indent {
    display: block;
    text-indent: 10px;
  }
</style>

