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
          <v-row>
            <v-col cols="6">
              <a
                href="https://play.google.com/store/apps/details?id=com.yasaidev.wiki_jump_game&pageId=104536201648276872752&pcampaignid=pcampaignidMKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1"
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
                href="https://play.google.com/store/apps/details?id=com.yasaidev.wiki_jump_game&pageId=104536201648276872752&pcampaignid=pcampaignidMKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1"
              >
                <v-img
                  contain
                  :height="$vuetify.breakpoint.xsOnly ? 40 : 60"
                  :src="require('../assets/appstore.png')"
                ></v-img>
              </a>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="12" md="6">
          <v-row justify="center">
            <v-carousel hide-delimiters interval="4000" cycle>
              <v-carousel-item
                v-for="image in screenshots"
                :key="image"
                :src="image"
                contain
              ></v-carousel-item>
            </v-carousel>
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
      <v-row class="pb-8">
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
    ],
    screenshots: [
      "/img/screenshot/screenshot0.png",
      "/img/screenshot/screenshot1.png",
      "/img/screenshot/screenshot2.png",
      "/img/screenshot/screenshot3.png",
    ],
  }),
  components: { AboutMeCard, HowToPlay },
};
</script>

<style scoped>
</style>