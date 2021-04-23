<template>
  <v-row>
    <v-col cols="6">
      <a
        href="https://play.google.com/store/apps/details?id=com.yasaidev.wiki_jump_game"
      >
        <v-img
          contain
          :height="$vuetify.breakpoint.xsOnly ? 40 : 60"
          :src="require('../assets/googleplay.png')"
        ></v-img
      ></a>
    </v-col>
    <v-col cols="6">
      <a
        href="https://apps.apple.com/jp/app/%E3%82%A6%E3%82%A3%E3%82%AD%E6%9C%80%E7%9F%AD%E5%88%B0%E9%81%94%E3%82%B2%E3%83%BC%E3%83%A0-%E3%82%A6%E3%82%A3%E3%82%AD%E7%9F%AD/id1563872394"
      >
        <v-img
          contain
          :height="$vuetify.breakpoint.xsOnly ? 40 : 60"
          :src="require('../assets/appstore.png')"
        ></v-img>
      </a>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "AppStoreButton",
};
</script>