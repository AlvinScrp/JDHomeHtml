<template>
  <div :title="isFullscreen ? '退出全屏' : '全屏'">
    <i class="sfont" :class="isFullscreen ? 'system-quanping' : 'system-quanping1'" @click="toggle"></i>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { useFullscreen } from '@vueuse/core'

export default defineComponent({
  name: 'fullscreen',
  setup() {
    const { isFullscreen, toggle } = useFullscreen()
    return {
      isFullscreen,
      toggle
    }
  }
})
</script>

<style lang="scss" scoped>
i {
  cursor: pointer;
  font-size: 18px;
  &:focus {
    outline: none;
  }
}
</style>
