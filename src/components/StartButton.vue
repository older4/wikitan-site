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
      const launch_uri = new URL("", "wikitan://topic");
      launch_uri.searchParams.append("start", this.startword);
      launch_uri.searchParams.append("end", this.endword);
      launch_uri.searchParams.append("lo", this.lo);
      window.open(launch_uri.href, "_blank");
    },
  },
};
</script>

<style>
</style>