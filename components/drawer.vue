<template>
  <v-layout>
    <v-navigation-drawer
      app
      temporary
      right
      :value="open && $vuetify.breakpoint.mdAndUp"
      color="green"
      @input="close($event)"
      class="details-drawer"
    >
      <v-container>
        <h1>Drawer</h1>
      </v-container>
    </v-navigation-drawer>

    <!-- mobile -->
    <v-dialog
      :value="open && $vuetify.breakpoint.smAndDown"
      fullscreen
      hide-overlay
      transition="dialog-bottom-transition"
    >
      <v-toolbar dark color="grey">
        <v-btn icon dark @click="$emit('close')">
          <v-icon>mdi-close</v-icon>
        </v-btn>
        <v-toolbar-title>Details</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items></v-toolbar-items>
      </v-toolbar>
      <h1>mobile</h1>
    </v-dialog>
  </v-layout>
</template>

<script>
export default {
  props: {
    open: {
      type: Boolean,
      open: false
    }
  },
  methods: {
    close($event) {
      if (!$event) {
        this.$emit('close')
      }
    }
  }
};
</script>