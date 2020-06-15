<template>
  <div class="full-width section-card volunteer">
    <div class="flex-center dark-blue-text section-title">
      <span>{{title}}</span>
    </div>

    <div class="flex-center bottom">
      <div class="flex-center paragraph">
        <p>“I am only one, but I am one. I cannot do everything, but I can do something. And I will not let what I cannot do interfere with what I can do.” – Edward Everett Hale</p>
        <p>Please send us an email with your details as you join our cause</p>
        <v-btn @click="sendEmail()" color="primary">EMAIL US</v-btn>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      title: "VOLUNTEER"
    };
  },
  methods: {
    sendEmail: () => {
      const email = "decassi@email.com";

      document.location = "mailto:" + email;
    }
  }
};
</script>

<style scoped>
.volunteer {
  margin-top: 20px;
  min-height: 250px;
  /* background: rgba(0, 0, 0, 0.04); */

  background: white;

  border-radius: 7px;
  margin-bottom: 60px;
}

.paragraph {
  width: 310px;
}
</style>