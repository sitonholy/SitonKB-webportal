·
<template>
  <div class="top-bar-container">
    <div>
      <div class="logo-container" @click="router.push('/')">
        <img src="@/assets/ic_zhishi_da.svg" />
        <div>知识库</div>
      </div>
      <TopMenu></TopMenu>
    </div>
  </div>
</template>
<script setup lang="ts">
import TopMenu from './top-menu/index.vue'
import { useRouter } from 'vue-router'

const router = useRouter()
</script>
<style lang="scss">
.top-bar-container {
  height: calc(100% - 36px);
  // height: var(--app-header-height);
  box-sizing: border-box;
  width: 116px;

  .app-title-container {
    margin-right: 45px;
  }

  .line {
    height: 2em;
  }
  .logo-container {
    height: 112px;
    text-align: center;
    background-color: #f4f7ff;
    display: flex;
    flex-direction: column;
    align-items: center;
    overflow: hidden;
    img {
      width: 32px;
      height: 32px;
      margin-top: 30px;
    }
    div {
      font-size: 16px;
      color: #034ce0;
      margin-top: 10px;
    }
  }
}
</style>
