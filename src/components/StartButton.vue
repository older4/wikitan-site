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
        setTimeout(function () {
          if (!document.webkitHidden) {
            window.location =
              "https://apps.apple.com/jp/app/%E3%82%A6%E3%82%A3%E3%82%AD%E6%9C%80%E7%9F%AD%E5%88%B0%E9%81%94%E3%82%B2%E3%83%BC%E3%83%A0-%E3%82%A6%E3%82%A3%E3%82%AD%E7%9F%AD/id1563872394";
          }
        }, 25);
        window.location = launch_uri;
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