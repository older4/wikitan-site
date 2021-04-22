<template>
  <v-btn color="success" x-large @click="launchApp()" class="font-weight-bold"
    >APPでスタート</v-btn
  >
</template>

<script>
export default {
  name: "StartButton",
  props: {
    startword: {
      type: String,
      required: true,
      default: "ボボボーボ・ボーボボ",
    },
    endword: {
      type: String,
      required: true,
      default: "ボボボーボ・ボーボボ",
    },
    lo: {
      type: String,
      required: true,
      default: "jp",
    },
  },
  methods: {
    launchApp() {
      // ios
      if (
        [
          "iPad Simulator",
          "iPhone Simulator",
          "iPod Simulator",
          "iPad",
          "iPhone",
          "iPod",
        ].includes(navigator.platform)
      ) {
        const launch_uri = `wikitan://topic?start=${encodeURIComponent(
          this.startword
        )}&end=${encodeURIComponent(this.endword)}&lo=jp`;
        document.location = launch_uri;
      }
      // android
      else {
        const launch_uri = `intent://topic?start=${encodeURIComponent(
          this.startword
        )}&end=${encodeURIComponent(this.endword)}&lo=jp`;
        window.open(
          `${launch_uri}#Intent;scheme=wikitan;package=com.yasaidev.wiki_jump_game;end`,
          "_blank"
        );
      }
    },
  },
};
</script>

<style>
</style>