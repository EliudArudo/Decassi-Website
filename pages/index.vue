<template>
  <div class="full-size">
    <Landing />

    <Vision />

    <Values />

    <Services />

    <Racism />

    <div class="full-width approach">&nbsp;</div>

    <div class="full-width volunteer">&nbsp;</div>
  </div>
</template>

<script>
import Landing from "@/components/Landing.vue";
import Vision from "@/components/Vision.vue";
import Values from "@/components/Values.vue";
import Services from "@/components/Services.vue";
import Racism from "@/components/Racism.vue";

export default {
  components: {
    Landing,
    Vision,
    Values,
    Services,
    Racism
  }
};
</script>

<style>
.approach {
  height: 250px;
  background: rgba(0, 0, 0, 0.04);
}

.volunteer {
  height: 300px;
  background: rgba(0, 0, 0, 0.07);

  margin-bottom: 30px;
}
</style>
