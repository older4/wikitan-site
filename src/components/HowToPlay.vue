<template>
  <v-card class="mx-auto" max-width="350" min-width="200" outlined>
    <v-carousel height="auto" :hide-delimiters="true">
      <v-carousel-item v-for="(item, index) in howtoplay" :key="index">
        <v-sheet height="100%">
          <v-img
            :src="item.image"
            contain
            height="300"
            class="grey lighten-1"
          ></v-img>

          <v-list light>
            <v-list-item>
              <v-list-item-avatar>
                <v-list-item-title>{{ index + 1 }}.</v-list-item-title>
              </v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title>{{ item.dec }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
  </v-card>
</template>

<script>
export default {
  name: "HowToPlay",
  data() {
    return {
      howtoplay: [
        { dec: "好きな単語を入力してスタート", image: "img/howto/howto0.png" },
        {
          dec: "項目を選択してゴールを目指せ！",
          image: "img/howto/howto1.png",
        },
        { dec: "ゴール！！！", image: "img/howto/howto2.png" },
      ],
    };
  },
};
</script>

<style>
</style>