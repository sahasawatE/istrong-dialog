<template>
  <v-card :color="color" :dark="dark">
    <v-card-text class="d-flex justify-center pt-4">
      <v-progress-linear
        indeterminate
        color="primary"
        rounded
        height="6px"
        :color="dark ? 'white' : 'primary'"
        v-if="linear"
      />
      <v-progress-circular
        v-else
        indeterminate
        color="primary"
        :color="dark ? 'white' : 'primary'"
      />
    </v-card-text>
    <v-card-actions class="d-flex px-4 pb-2 justify-center">
      {{ text }}
    </v-card-actions>
  </v-card>
</template>

<script>
import { VCard, VCardText, VProgressLinear } from "vuetify/lib";

export default {
  layout: [
    "default",
    {
      hideOverlay: true,
      persistent: true,
      width: 300,
    },
  ],
  components: {
    VCard,
    VCardText,
    VProgressLinear,
  },
  props: {
    text: String,
    dark: {
      type: Boolean,
      default: true,
    },
    color: String,
    linear: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
