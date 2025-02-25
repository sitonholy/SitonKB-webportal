<template>
  <div class="app-header" :class="!isDefaultTheme ? 'custom-header' : ''">
    <el-alert
      v-if="user.isExpire()"
      :title="$t('layout.isExpire')"
      type="warning"
      class="border-b"
      show-icon
      :closable="false"
    />
    <TopBar />
    <!-- <div style="padding: 0 10px">
      <el-button type="primary" style="width: 100%"> 退出 </el-button>
    </div> -->
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import TopBar from '../top-bar/index.vue'
import useStore from '@/stores'
const { user } = useStore()
const isDefaultTheme = computed(() => {
  return user.isDefaultTheme()
})
</script>

<style lang="scss" scoped>
.app-header {
  // height: calc(100% - 112px);
  box-sizing: border-box;
  overflow-y: auto;
  background-color: #e9effe;
  // position: fixed;
  // width: 100%;
  // left: 0;
  // top: 0;
  // z-index: 100;
}
</style>
