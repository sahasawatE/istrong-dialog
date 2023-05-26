<template>
  <v-card tile>
    <v-card-title>
      <v-row>
        <v-col>
          <div class="d-flex justify-center my-3">
            <img :src="image" height="30%" />
          </div>
        </v-col>
      </v-row>
    </v-card-title>

    <v-card-text>
      <v-row>
        <v-col :cols="12" class="d-flex justify-center">
          <div class="font-weight-black text-h6 black--text">
            {{ title }}
          </div>
        </v-col>
      </v-row>
      <v-row>
        <v-col :cols="12" class="d-flex justify-center">
          <p class="primary--text">
            {{ text }}
          </p>
        </v-col>
      </v-row>
    </v-card-text>

    <DialogActions :actions="actions" v-bind="actionOptions" />
  </v-card>
</template>
<script>
import Confirmable from "vuedl/src/mixins/confirmable";
import Colorable from "../mixins/colorable";
import Iconable from "../mixins/iconable";
import DialogActions from "./DialogActions.vue";
import {
  VCard,
  VCardText,
  VCardTitle,
  VCardText,
  VIcon,
  VRow,
  VCol,
} from "vuetify/lib";
export default {
  components: {
    DialogActions,
    VCard,
    VCardText,
    VCardTitle,
    VCardText,
    VIcon,
  },
  layout: ["default", { width: 450 }],
  mixins: [Iconable, Confirmable, Colorable],
  props: {
    image: {
      type: [String, Object],
      required: false,
      default: "",
    },
  },
};
</script>
<style></style>
