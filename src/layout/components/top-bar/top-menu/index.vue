<template>
  <div class="side-menu-container">
    <MenuItem
      :menu="menu"
      v-hasPermission="menu.meta?.permission"
      v-for="(menu, index) in topMenuList"
      :key="index"
    >
    </MenuItem>
  </div>
</template>
<script setup lang="ts">
import { computed } from 'vue'
import { getChildRouteListByPathAndName } from '@/router/index'
import MenuItem from './MenuItem.vue'

const topMenuList = computed(() => {
  return getChildRouteListByPathAndName('/', 'home')
})
</script>
<style lang="scss" scoped>
.side-menu-container {
  height: calc(100% - 112px);
  box-sizing: border-box;
  overflow-y: auto;
}
</style>
