<template>
  <div class="full-width vision">
    <div class="flex-center dark-blue-text section-title">
      <span>{{title}}</span>
    </div>

    <div class="flex-center bottom">
      <div class="flex-center paragraph" v-for="(item, index) of items" :key="`vision-${index}`">
        <v-icon class="animated section-icon" color="primary">{{item.icon}}</v-icon>
        <h4 class="dark-blue-text">{{item.title}}</h4>
        <p>{{item.content}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      title: "VISION, MISSION AND CORE VALUES",
      items: [
        {
          icon: "remove_red_eye",
          title: "OUR VISION",
          content:
            "A world class mental and behavioral health service foundation providing critical services to the most vulnerable, marginalized, excluded minority groups in the region"
        },
        {
          icon: "near_me",
          title: "OUR MISSION",
          content:
            "To provide a broad range of quality, timely and accessible mental and behavioral health services to the vulnerable, marginalized and excluded population pockets in our society"
        }
      ]
    };
  }
};
</script>

<style scoped>
.vision {
  margin-top: 20px;
  min-height: 250px;
  /* background: rgba(0, 0, 0, 0.04); */
}

.bottom {
  flex-wrap: wrap;
}
</style>