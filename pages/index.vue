<template>
  <div class="full-size">
    <Landing />

    <Vision />

    <Values />

    <Services />

    <Racism />

    <Approach />

    <Volunteer />
  </div>
</template>

<script>
import Landing from "@/components/Landing.vue";
import Vision from "@/components/Vision.vue";
import Values from "@/components/Values.vue";
import Services from "@/components/Services.vue";
import Racism from "@/components/Racism.vue";
import Approach from "@/components/Approach.vue";
import Volunteer from "@/components/Volunteer.vue";

export default {
  components: {
    Landing,
    Vision,
    Values,
    Services,
    Racism,
    Approach,
    Volunteer
  }
};
</script>

<style>
</style>

