<template>
  <article class="main-content">
    <slot />
  </article>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'SlAside'
})
</script>

<style lang="scss" scoped>
.main-content {
  padding: 0 10px;
}
</style>
