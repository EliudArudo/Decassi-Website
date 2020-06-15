<template>
  <div class="full-width approach">
    <div class="flex-center bottom">
      <div
        class="flex-center paragraph"
        v-for="(approach, index) of approaches"
        :key="`approach-${index}`"
      >
        <h4 class="dark-blue-text">{{approach.title}}</h4>
        <p>{{approach.content}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      approaches: [
        {
          title: "OUR APPROACH",
          content:
            "We listen and integrate our clients’ health experience in providing practical solutions to their health challenges arising out of their marginalization and exclusion We conduct effective and robust outreach programs to provide clients with the much needed services"
        },
        {
          title: "OUR CLIENTS",
          content:
            "The marginalized, excluded and minority groups including immigrants (dreamers, asylum seekers, and illegal immigrants), felons, rural farm workers, single parents, the elderly and veterans"
        }
      ]
    };
  }
};
</script>

<style scoped>
.approach {
  margin-top: 30px;
  min-height: 250px;
  /* background: rgba(0, 0, 0, 0.04); */
}

.bottom {
  align-items: flex-start;
  flex-wrap: wrap;
}
</style>