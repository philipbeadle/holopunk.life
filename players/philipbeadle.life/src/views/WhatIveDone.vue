<template>
  <core-section id="what-ive-done">
    <abstract-3 />

    <core-heading>What I've done</core-heading>

    <v-col cols="12">
      <v-carousel
        :cycle="true"
        :height="schema.projectsCarousel * this.carouselHeight"
        :show-arrows="false"
        class="elevation-0"
        hide-delimiter-background
      >
        <v-carousel-item v-for="(project, i) in schema.projects" :key="i">
          <project :value="project" />
        </v-carousel-item>
      </v-carousel>
    </v-col>
  </core-section>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'WhatIveDone',

  components: {
    Abstract3: () => import('@/components/Abstract3'),
    Project: () => import('@/components/Project')
  },
  mounted () {
    console.log(this.$vuetify.breakpoint.name)
  },
  computed: {
    ...mapState('app', ['schema']),
    carouselHeight () {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs': return '1000'
        case 'sm': return '900'
        case 'md': return '900'
        case 'lg': return '650'
        case 'xl': return '600'
      }
      return '1000'
    }
  }
}
</script>
