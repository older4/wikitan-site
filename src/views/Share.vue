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
        <v-col cols="12">
          <v-row justify="center"
            ><v-img
              @click="$router.push('/')"
              :src="require('../assets/title.png')"
              style="cursor: pointer"
              max-height="200"
              contain
            >
            </v-img>
          </v-row>
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
        </v-col>
      </v-row>
    </v-container>
    <v-container>
      <v-row>
        <v-col cols="12">
          <h2
            class="text-center text-md-h3 text-sm-h4 text-h5 black--text font-weight-bold"
          >
            お題
          </h2></v-col
        >
        <v-col cols="12">
          <TopicCard :startword="startword" :endword="endword"></TopicCard>
        </v-col>
      </v-row>
      <v-row align="center" justify="center" align-content="center">
        <StartButton
          :startword="startword"
          :endword="endword"
          :lo="lo"
        ></StartButton>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import TopicCard from "../components/TopicCard";
import StartButton from "../components/StartButton";

export default {
  components: {
    TopicCard: TopicCard,
    StartButton: StartButton,
  },
  data() {
    return {
      startword: "",
      endword: "",
      lo: "",
    };
  },
  mounted() {
    if (
      this.$route.query.start != undefined &&
      this.$route.query.end != undefined &&
      this.$route.query.lo != undefined
    ) {
      this.startword = this.$route.query.start;
      this.endword = this.$route.query.end;
      this.lo = this.$route.query.lo;
    } else {
      this.$router.push("/");
    }
    document
      .querySelector("meta[property='og:image']")
      .setAttribute(
        "content",
        `https://res.cloudinary.com/yasaidev/image/upload/q_80/c_fit,h_200,l_text:Sawarabi%20Gothic_64:${encodeURIComponent(
          this.startword
        )},co_rgb:252525,w_937,y_-150/c_fit,h_200,l_text:Sawarabi%20Gothic_64:${encodeURIComponent(
          this.endword
        )},co_rgb:252525,w_937,y_90/v1619020654/%E3%82%A6%E3%82%A3%E3%82%AD%E7%9F%AD/wikitan_twitter_card_cla0hs.png`
      );
    document
      .querySelector("meta[property='og:description']")
      .setAttribute(
        "content",
        `${this.startword}から${this.endword}にあなたはいけますか？`
      );
  },
};
</script>

<style>
</style>