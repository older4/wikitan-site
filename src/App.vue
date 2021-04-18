<template>
  <v-app>
    <v-main>
      <router-view />
    </v-main>
    <v-footer dark padless>
      <v-card class="flex" flat tile>
        <v-card-title class="cyan darken-2">
          <strong class="subheading">電気野菜</strong>

          <v-spacer></v-spacer>

          <a
            :href="item.url"
            v-for="item in icons"
            :key="item.icon"
            class="text-decoration-none"
          >
            <v-icon size="24px" class="mx-4"> {{ item.icon }}</v-icon></a
          >
        </v-card-title>

        <v-card-text class="py-2 white--text text-center">
          {{ new Date().getFullYear() }} — <strong>YasaiDev/電気野菜</strong>
          <h1 class="text-body-2 white--text text-center">
            ウィキペディア最短到達ゲーム
          </h1>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    icons: [
      { icon: "mdi-twitter", url: "https://twitter.com/YasaiDev" },
      {
        icon: "mdi-youtube",
        url: "https://www.youtube.com/channel/UCPF7iypT3fMEjOd4h-iQUrQ",
      },
    ],
  }),
};
</script>
