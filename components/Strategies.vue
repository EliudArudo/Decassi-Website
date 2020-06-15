<template>
  <div class="full-width strategies">
    <div class="flex-center dark-blue-text section-title">
      <span>{{title}}</span>
    </div>

    <div class="flex-center bottom">
      <div
        class="flex-center paragraph"
        v-for="(strategy, index) of strategies"
        :key="`strategy-${index}`"
      >
        <v-icon class="section-icon" color="primary">{{strategy.icon}}</v-icon>
        <h4 class="dark-blue-text strategy-title">{{strategy.title}}</h4>

        <p class="flex-center">
          <span
            v-for="(content, index2) of strategy.content"
            :key="`content-${index}-${index2}`"
          >{{content}}</span>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      title: "OUR RESOURCE MOBILIZATION AND PARTNERSHIP STRATEGIES",
      strategies: [
        {
          icon: "recent_actors",
          title: "Deepening relations with existing donors/sponsors",
          content: [
            "Steward relations with traditional donors",
            "Deepen relations with the agency’s diversified donor base 8 regional member states are essential partners",
            "(re)foster emergent donor relations 8 other non-traditional donors remain important continuing partners"
          ]
        },
        {
          icon: "monetization_on",
          title: "Diversifying donor base for new funding streams",
          content: [
            "Developing further private partnerships",
            "Expanding existing partnerships and exploration of new partnerships",
            "Engagement in mental health policy forums"
          ]
        },
        {
          icon: "work",
          title: "Internal capacity for resource mobilization",
          content: [
            "Mainstreaming resource mobilization in all departments/units",
            "Harmonizing messaging  of mental health issues/services",
            "Communication and visibility",
            "Peer approach",
            "Improving documentation of cases",
            "Establishing  mechanism to protect resource fluctuations"
          ]
        },
        {
          icon: "people",
          title: "Community outreach initiatives/events",
          content: [
            "Yard sale",
            "Raffles",
            "Caribbean food festival",
            "Talent and step show",
            "Car wash"
          ]
        }
      ]
    };
  }
};
</script>

<style scoped>
.strategies {
  margin-top: 20px;
  margin-bottom: 40px;
  min-height: 250px;
  /* background: rgba(0, 0, 0, 0.04); */
}

.bottom {
  margin-top: 20px;
  align-items: flex-start;
  flex-wrap: wrap;
}

.strategy-title {
  text-transform: uppercase;
}

p {
  margin-top: 15px;

  flex-direction: column;
}

p span {
  margin-top: 5px;
}
</style>