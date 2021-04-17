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
            ><v-img
              @click="$router.push('/')"
              :src="require('../assets/title.png')"
              style="cursor: pointer"
              contain
            >
            </v-img>
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
      // this.$router.push("/");
    }
  },
};
</script>

<style>
</style>