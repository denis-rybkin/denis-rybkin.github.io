<template>
  <section class="resume-item grid-wrapper">
    <aside
      class="resume-item-dates xs-grid-column-span-14 sm-grid-column-span-4 md-grid-column-span-14 lg-grid-column-span-4"
    >
      <slot name="dates" />
    </aside>
    <div
      class="resume-item-details xs-grid-column-span-14 sm-grid-column-span-10 md-grid-column-span-14 lg-grid-column-span-10"
    >
      <header>
        <h3 class="position"><slot name="position" /></h3>
        <h4 class="company"><slot name="company" /></h4>
      </header>
      <div class="description">
        <slot name="description" />
      </div>
      <div class="tags">
        <slot name="tags" />
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ResumeItem'
})
</script>

<style lang="scss" scoped>
.resume-item {
  padding: 15px 0;
  border-radius: 4px;
  border-top: 2px solid transparent;
  background-color: transparent;
  transition: background-color 0.1s;

  .company {
    opacity: 0.8;
  }

  &-dates,
  &-details {
    padding: 0 10px;
  }

  &-details {
    header {
      margin-bottom: 4px;
    }
  }

  &-dates {
    opacity: 0.5;
  }

  .description {
    opacity: 0.7;
  }

  &:hover {
    background-color: #fff1;
    border-top-color: #fff1;

    .resume-item--dates {
      opacity: 0.9;
    }

    .description {
      opacity: 0.9;
    }
  }

  & + & {
    margin-top: 20px;
  }
}
</style>
