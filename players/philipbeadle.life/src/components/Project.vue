<template>
  <v-sheet
    class="py-md-5"
    height="100%"
    color="transparent"
  >
    <div class="text-center mb-5">
      <core-subheading
        class="mb-1"
        v-text="value.name"
      />
      <span
        class="subheading"
        v-text="value.category"
      />
    </div>
    <v-row>
      <v-col v-if="value.src" class="hidden-lg-and-up">
        <v-img
          :src="require(`@/assets/projects/${value.src}`)"
          height="200"
          width="500"
          contain
          class="mx-auto"
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="auto">
        <div class="mb-3" style="max-width: 500px;">
          <core-subheading class="mb-3">
            Project Details
          </core-subheading>
          <core-text v-text="value.description" />
          <core-subheading>
            Project Info
          </core-subheading>
          <v-list class="transparent">
            <v-list-item>
              <v-list-item-action v-if="$vuetify.breakpoint.smAndUp">
                <v-icon color="primary">
                  mdi-account
                </v-icon>
              </v-list-item-action>
              <v-list-item-title class="mr-2">
                Client Name
              </v-list-item-title>
              <v-list-item-title v-text="value.client" class="caption grey--text text--lighten-1" />
            </v-list-item>
            <v-list-item>
              <v-list-item-action v-if="$vuetify.breakpoint.smAndUp">
                <v-icon color="primary">
                  mdi-tag
                </v-icon>
              </v-list-item-action>
              <v-list-item-title class="mr-2">
                Project Category
              </v-list-item-title>
              <v-list-item-title v-text="value.category" class="caption grey--text text--lighten-1" />
            </v-list-item>
            <v-list-item>
              <v-list-item-action v-if="$vuetify.breakpoint.smAndUp">
                <v-icon color="primary">
                  mdi-teamviewer
                </v-icon>
              </v-list-item-action>
              <v-list-item-title class="mr-2">
                Team Setup
              </v-list-item-title>
              <v-list-item-title v-text="value.team" class="caption grey--text text--lighten-1"/>
            </v-list-item>
          </v-list>
        </div>
      </v-col>
      <v-col v-if="value.src" class="hidden-md-and-down">
        <v-img
          :src="require(`@/assets/projects/${value.src}`)"
          height="350"
          width="500"
          contain
          class="mx-auto"
        />
      </v-col>
    </v-row>
  </v-sheet>
</template>

<script>
export default {
  props: {
    value: {
      type: Object,
      default: () => ({
        name: '',
        category: '',
        src: undefined
      })
    }
  }
}
</script>
