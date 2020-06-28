<template>
  <div class="full-width flex-center section-card racism">
    <div class="flex-center top">
      <div class="flex-center section-icons">
        <v-icon class="animated section-icon" dark>person</v-icon>
        <v-icon class="animated section-icon" dark>person_outline</v-icon>
      </div>

      <h4 class="white-text">{{title}}</h4>
    </div>

    <div class="bottom">
      <div class="flex-center effects-wrapper">
        <div
          class="flex-center paragraph"
          v-for="(effect, index) of effects"
          :key="`racism-${index}`"
        >
          <p>{{effect}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "EFFECTS OF RACISM ON MINORITY",
      effects: [
        "Disadvantaging the nondominant group through power used by the dominant group to provide members of the group with advantages",
        "Structural racism still exists after the Jim Crow era, which significantly disadvantages them while limiting their access to health care",
        "Women having higher poverty rates than men in the United States in every state except Colorado and Idaho",
        "Even if minority women are hired, they are disproportionately employed in low-paying occupations, such as childcare, nursing, cleaning, waitressing, and teaching",
        "The minority have limited access to health care even after the implementation of the Affordable Care Act because they do not have health insurance from their jobs",
        "Increased rates of disease and disability in people of color. Racism results in increased stress which impairs their health status",
        "Increased stress from perceived racism also affects birth outcomes by increasing African Americans’ rates of infant mortality",
        "Health disparities caused by the social determinants of health which are outside an individual’s control"
      ]
    };
  }
};
</script>

<style scoped>
.racism {
  min-height: 350px;
  margin-top: 40px;

  border-radius: 7px;

  background: rgba(0, 0, 0, 0.07);

  color: white;

  flex-direction: column;

  background: white url("~@/assets/img/backgrounds/racism.jpg") no-repeat center;
  transform: translate(0, 0, 0);
}

.racism .top {
  height: 80px;
  margin-top: 20px;

  flex-direction: column;
}

.effects-wrapper {
  flex-wrap: wrap;
}

.effects-wrapper .paragraph {
  min-height: 110px;
}
</style>