<template>
  <core-section id="what-my-clients-say">
    <abstract-4 />
    <core-heading>What my clients say.</core-heading>
    <v-col
      v-for="(client, i) in schema.clients" :key="`quote-${i}`" cols="12" sm="4">
      <client :value="client" />
    </v-col>
    <template v-if="schema.awards.length">
      <core-subheading>Awards</core-subheading>
      <v-col v-for="(award, i) in schema.awards" :key="`award-${i}`" cols="12" sm="3">

      </v-col>
    </template>
  </core-section>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'WhatMyClientsSay',

  components: {
    Abstract4: () => import('@/components/Abstract4'),
    Client: () => import('@/components/Client')
  },
  computed: {
    ...mapState('app', ['schema'])
  }
}
</script>
