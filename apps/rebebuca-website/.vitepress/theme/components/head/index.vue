<script lang="ts" setup>
import { ref } from 'vue'
import { Logo } from '@m7s/ui/vue'
import data from '../constants'
const config = ref(data)
</script>

<template>
  <!--顶部导航 -->
  <div class="main">
    <div class="box">
      <div class="left">
        <img src="/images/logo.png" alt="" srcset="">
        <div class="logo">Rebebuca</div>
      </div>
      <div class="right">
        <div v-for="(item, index) in config" :key="index" class="item">
          <template v-if="item.children">
            <span>{{ item.name }}</span>
            <div class="nav-sheet-container">
              <a
                :href="j.url"
                v-for="(j, i) in item.children"
                :key="i"
                class="nav-sheet-item"
                >{{ j.name }}</a
              >
            </div>
          </template>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="less" scoped src="./index.less"></style>
