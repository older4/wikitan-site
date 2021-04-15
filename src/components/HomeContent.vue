<template>
  <div>
    <h2 class="text-md-h2 text-h4 black--text text-center">作者</h2>
    <h3 class="text-md-h4 text-h6 black--text text-center pt-4">電気野菜</h3>
    <div class="pb-10">
      <ul>
        <li
          v-for="item in this.SNS_Links"
          :key="item.icon"
          class="text-center text-body-1 black--text"
        >
          <a :href="item.url" class="text-decoration-none">
            <v-icon size="24px" :color="item.color"> {{ item.icon }}</v-icon
            >{{ item.name }}</a
          >
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeContent",
  props: {
    SNS_Links: {
      type: Object,
      required: true,
    },
  },
  data: () => ({}),
};
</script>
