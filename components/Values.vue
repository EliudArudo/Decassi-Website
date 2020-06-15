<template>
  <div class="full-width flex-center values">
    <v-icon class="animated section-icon" color="primary">gavel</v-icon>
    <h4 class="dark-blue-text">{{title}}</h4>

    <div class="flex-center paragraph-list-wrapper">
      <div
        class="flex-center small-paragraph"
        v-for="(value, index) of values"
        :key="`small-${index}`"
      >
        <div class="flex-center initial">
          <span>{{value.charAt(0)}}</span>
        </div>
        <div class="paragraph-content">
          <p>{{value}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "OUR CORE VALUES",
      values: [
        "Respect for the uniqueness and cultural backgrounds of each client",
        "Empathy in the provision of quality and accessible services",
        "Spirituality in the improvement of health and well being",
        "Professionalism in partnering with clients and other organizations",
        "Encourage healthy life choices and social inclusion in the use of our resources",
        "Commitment to serve the vulnerable, marginalized, excluded clients",
        "Teamwork and collaboration both internally and externally"
      ]
    };
  }
};
</script>

<style scoped>
.values {
  margin-top: 30px;
  min-height: 200px;
  /* background: rgba(0, 0, 0, 0.07); */

  flex-direction: column;
}

.small-paragraph {
  position: relative;
}

.initial {
  height: 100px;
  width: 100px;

  text-transform: uppercase;

  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  margin: auto;

  background: rgba(51, 180, 227, 0.1);
  border-radius: 50%;

  font-size: 60px;
  color: #fcfcfc;
}

.paragraph-content {
  z-index: 2;

  font-weight: 500;
}

.paragraph-list-wrapper {
  flex-wrap: wrap;
}
</style>