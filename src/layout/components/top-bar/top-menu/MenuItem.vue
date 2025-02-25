<template>
  <div
    class="menu-item-container"
    :class="isActive ? 'active' : ''"
    @click="router.push({ name: menu.name })"
  >
    <!-- <div class="icon">
      <AppIcon :iconName="menu.meta ? (menu.meta.icon as string) : '404'" />
    </div> -->
    <div class="title">
      {{ $t(menu.meta?.title as string) }}
    </div>
  </div>
</template>
<script setup lang="ts">
import { useRouter, useRoute, type RouteRecordRaw } from 'vue-router'
import { computed } from 'vue'
const router = useRouter()
const route = useRoute()

const props = defineProps<{
  menu: RouteRecordRaw
}>()

const isActive = computed(() => {
  const { name, path, meta } = route
  return (name == props.menu.name && path == props.menu.path) || meta?.activeMenu == props.menu.path
})
</script>
<style lang="scss" scoped>
.menu-item-container {
  cursor: pointer;
  font-size: 14px;
  position: relative;
  height: 40px;
  line-height: 40px;
  text-align: center;

  .icon {
    font-size: 15px;
    margin-right: 5px;
    margin-top: 2px;
  }

}

.active {
  color: var(--el-color-primary);
  background-image: linear-gradient(90deg, #89a9f1 0%, #4980fb 100%);
  color: #ffffff !important;
}
</style>
