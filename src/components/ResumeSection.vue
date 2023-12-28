<template>
  <article class="section-experience">
    <slot />
  </article>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ResumeSection'
})
</script>

<style lang="scss" scoped>
.section-experience {
  margin-top: 40px;
  padding: 20px 0;
}
</style>
