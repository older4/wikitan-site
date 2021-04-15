<template>
  <v-app>
    <v-main>
      <router-view />
      <router-view name="Home" />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    //
  }),
};
</script>
