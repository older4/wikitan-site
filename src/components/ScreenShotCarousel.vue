<template>
  <v-carousel hide-delimiters interval="4000" cycle>
    <v-carousel-item
      v-for="image in screenshots"
      :key="image"
      :src="image"
      width="100%"
      max-height="auto"
      contain
    ></v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  name: "ScreenShotCarousel",
  data() {
    return {
      screenshots: [
        "/img/screenshot/screenshot0.png",
        "/img/screenshot/screenshot1.png",
        "/img/screenshot/screenshot2.png",
        "/img/screenshot/screenshot3.png",
      ],
    };
  },
};
</script>

<style>
</style>