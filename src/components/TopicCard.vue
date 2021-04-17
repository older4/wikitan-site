<template>
  <v-card class="mx-auto" max-width="500" min-width="300">
    <v-card-subtitle class="pb-0 py-2">初めの単語</v-card-subtitle>
    <v-card-title primary-title class="pt-0 py-2">
      {{ startword }}
    </v-card-title>
    <v-divider></v-divider>
    <v-card-subtitle class="pb-0 py-2">終わりの単語</v-card-subtitle>
    <v-card-title primary-title class="pt-0 py-2">
      {{ endword }}
    </v-card-title>
  </v-card>
</template>

<script>
export default {
  name: "TopicCard",
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
  },
};
</script>

<style>
</style>