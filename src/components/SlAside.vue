<template>
  <div class="heading-block sticky">
    <h1>{{ name }}</h1>
    <h2>{{ occupation }}</h2>
    <p class="mt">
      <slot />
    </p>

    <a
      v-if="resumeLink"
      class="resume-link"
      :href="resumeLink"
      target="_blank"
      rel="noopener noreferrer"
    >
      <font-awesome-icon :icon="['far', 'file']" /> <span>Resume</span>
    </a>

    <div class="links">
      <section class="links-socials">
        <a v-for="(social, i) in socials" :key="i" class="link" :href="social.href" target="_blank">
          <font-awesome-icon :icon="social.icon" />
        </a>
      </section>
    </div>
  </div>
</template>

<script lang="ts">
import type { Social } from '@/content'
import { defineComponent, type PropType } from 'vue'
export default defineComponent({
  name: 'SlAside',
  props: {
    name: {
      type: String,
      required: true,
    },
    occupation: {
      type: String,
      required: true,
    },
    socials: {
      type: Array as PropType<Social[]>,
      default: () => []
    },
    resumeLink: {
      type: String,
      required: false
    }
  }
})
</script>

<style lang="scss" scoped>
@import '/src/assets/mixins.scss';
@import '/src/assets/grid.scss';

.heading-block {
  padding: 0 10px;
}

.sticky {
  position: sticky;
  top: 20px;
  
  @include media-breakpoint-up(lg) {
    height: calc(100vh);
    top: 80px;

    height: calc(100vh - 80px);
    min-height: 340px;
  }
}

.mt {
  margin-top: 2rem;
}

.resume-link {
  display: block;
  margin: 15px 0;
  text-decoration: none;
  opacity: 0.4;

  span {
    text-decoration: underline;
  }

  &:hover {
    opacity: 0.7;
  }
}

p {
  opacity: 0.7;
}

.links {
  margin-top: 30px;

  @include media-breakpoint-up(lg) {
    position: absolute;
    bottom: 60px;
  }

  &-socials {
    margin-bottom: 10px;
  }

  .link {
    font-size: 1.6rem;
    padding: 2px;
    opacity: 0.5;
    transition: opacity 0.2s;

    &:hover {
      opacity: 0.7;
    }

    & + .link {
      margin-left: 10px;
    }
  }
}
</style>
