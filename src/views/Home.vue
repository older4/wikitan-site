<template>
  <div>
    <v-container
      fill-height
      fluid
      style="background-color: #02bdd4"
      pt-12
      pb-8
      px-8
    >
      <v-row align="center">
        <v-col cols="12" md="6">
          <v-row justify="center"
            ><v-img :src="require('../assets/title.png')" contain> </v-img>
          </v-row>
          <v-row justify="center">
            <v-col cols="12">
              <p
                class="text-center text-md-h5 text-sm-h6 text-body-1 white--text font-weight-bold pt-5"
              >
                雑学が身につくアプリ
              </p>
              <p
                class="text-center text-md-h5 text-sm-h6 text-body-1 font-weight-bold white--text"
              >
                自分だけの最短ルートを見つけろ！
              </p>
            </v-col>
          </v-row>
          <AppStoreButton></AppStoreButton>
        </v-col>
        <v-col cols="12" md="6">
          <v-row justify="center">
            <ScreenShotCarousel></ScreenShotCarousel>
          </v-row>
        </v-col>
      </v-row>
    </v-container>

    <v-container fluid class="pt-8">
      <v-row align-content="center">
        <v-col>
          <h2 class="text-md-h3 text-h4 black--text text-center">遊び方</h2>
        </v-col>
      </v-row>
      <v-row class="pb-8 px-4">
        <HowToPlay></HowToPlay>
      </v-row>
      <v-row align-content="center">
        <v-col>
          <h2 class="text-md-h3 text-h4 black--text text-center">作者</h2>
        </v-col>
      </v-row>
      <v-row class="pb-8">
        <AboutMeCard :SNS_Links="icons"></AboutMeCard>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import AboutMeCard from "@/components/AboutMeCard";
import HowToPlay from "../components/HowToPlay";
import ScreenShotCarousel from "../components/ScreenShotCarousel";
import AppStoreButton from "../components/AppStoreButton";
// @ is an alias to /src

export default {
  name: "Home",
  data: () => ({
    icons: [
      {
        icon: "mdi-twitter",
        url: "https://twitter.com/YasaiDev",
        name: "@YasaiDev",
        color: "blue",
      },
      {
        icon: "mdi-youtube",
        url: "https://www.youtube.com/channel/UCPF7iypT3fMEjOd4h-iQUrQ",
        name: "電気野菜チャンネル",
        color: "red",
      },
      {
        icon: "mdi-home",
        url: "https://yasaidev.work",
        name: "電気野菜 Logs",
        color: "gray",
      },
    ],
  }),
  components: { AboutMeCard, HowToPlay, ScreenShotCarousel, AppStoreButton },
};
</script>

<style scoped>
</style>