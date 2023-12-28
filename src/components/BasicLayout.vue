<template>
  <div class="layout grid-wrapper">
    <header class="aside xs-grid-column-span-14 md-grid-column-span-5">
      <slot name="aside" />
    </header>
    <main class="main xs-grid-column-span-14 md-grid-column-span-9">
      <slot />
    </main>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'BasicLayout',

  setup() {}
})
</script>

<style lang="scss" scoped>
@import '/src/assets/mixins.scss';
@import '/src/assets/grid.scss';

.layout {
  position: relative;
  max-width: 1024px;
  width: 100%;
  margin: 0 auto;
}
.wrapper {
  min-height: 100vh;
}

.main,
.aside {
  position: relative;
  padding: 20px 20px 0px;
  
  @include media-breakpoint-up(lg) {
    padding: 80px 20px 0px;
  }
}

.main {
  position: relative;
  min-height: 400px;
}
</style>
