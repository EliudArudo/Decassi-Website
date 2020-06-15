<template>
  <div class="full-width section-card services" id="services">
    <div class="flex-center dark-blue-text section-title">
      <span>{{title}}</span>
    </div>

    <div class="flex-center services-wrapper">
      <div
        class="flex-center service"
        v-for="(service, index) of services"
        :key="`service-${index}`"
      >
        <div
          class="section-card"
          :style="{'background-image': 'url(' + require(`@/assets/img/services/${service.picture}`) + ')'}"
        ></div>

        <p>{{service.title}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "SERVICES WE OFFER",
      services: [
        {
          picture: "life-coach.png",
          title: "Life coach services"
        },
        {
          picture: "substance-abuse.png",
          title: "Substance abuse services"
        },
        {
          picture: "mental-services.png",
          title: "Mental and behavioral health services for qualified appliance"
        },
        {
          picture: "financial-help.png",
          title:
            "Referrals and linkages to food, housing, clothing, financial and occupational needs"
        },
        {
          picture: "financial-literacy.png",
          title: "Financial literacy"
        }
      ]
    };
  }
};
</script>

<style scoped>
.services {
  /* height: 300px; */
  background: #fcfcfc;

  border-radius: 7px;

  flex-direction: column;
}

.services-wrapper {
  align-items: flex-start;
  flex-wrap: wrap;
}

.service {
  flex-direction: column;
  margin: 20px;
}

.service .section-card {
  height: 150px;
  width: 150px;

  margin-bottom: 10px;

  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;

  border-radius: 7px;
  box-shadow: 0px 1px 10px rgba(0, 0, 0, 0.2);
}

.service p {
  font-weight: 600;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
  width: 130px;
}
</style>