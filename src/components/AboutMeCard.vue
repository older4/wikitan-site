<template>
  <v-card class="mx-auto" max-width="350" outlined min-width="150">
    <div class="d-flex flex-no-wrap justify-space-between">
      <div>
        <v-card-title primary-title class="pb-0"> 電気野菜 </v-card-title>
        <a
          :href="item.url"
          v-for="item in this.SNS_Links"
          :key="item.icon"
          class="text-body-1 black--text pt-0 text-decoration-none"
          cols="12"
          ><v-card-text class="text--primary py-0"
            ><v-icon size="24px" :color="item.color"> {{ item.icon }}</v-icon
            >{{ item.name }}</v-card-text
          ></a
        >
      </div>
      <v-avatar class="ma-3" size="125" tile>
        <v-img contain :src="require('../assets/avatar.jpg')" class="mx-auto">
        </v-img>
      </v-avatar>
    </div>
  </v-card>
</template>

<script>
export default {
  name: "AboutMeCard",
  props: {
    SNS_Links: {
      type: Array,
      required: true,
    },
  },
  data: () => ({}),
};
</script>
