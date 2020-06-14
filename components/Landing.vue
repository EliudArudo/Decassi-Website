<template>
  <div class="full-width flex-center landing" id="landing">
    <div class="flex-center top">
      <div class="flex-center logo-title">
        <img src="@/assets/img/logo.svg" alt="Logo" />

        <div class="flex-center dark-blue-text title-wrapper">
          <span class="title-fix">
            De
            <span class="light-blue-text">Cassi</span>
          </span>
          <span>Foundation</span>
        </div>
      </div>

      <div class="landing-text">
        <span
          class="white--text"
        >For the vulnerable, disenfranchised, underserved and disempowered members of the society</span>
      </div>
    </div>

    <div class="bottom">
      <div class="flex-center landing-infos">
        <div class="flex-center paragraph">
          <h4>WHO WE ARE</h4>
          <p>We are a mental and behavioural health services provider offering comprehensive services to the vulnerable population who typically do not qualify for government subsidized services and occupational and education programs</p>
        </div>

        <div class="flex-center paragraph">
          <h4>WHAT WE BELIEVE</h4>
          <p>
            Limited mental and behavioural health services are the most constant phenomena among the most vulnerable, marginalized and excluded minority groups.
            They must be included in this is critical health service component
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {}
};
</script>  

<style scoped>
.landing {
  height: 70vh;
  max-height: 700px;

  flex-direction: column;

  background: white;
  box-shadow: 0px 0px 2px 3px rgba(0, 0, 0, 0.02);
  border-radius: 0px 0px 7px 7px;

  background: white url("~@/assets/img/backgrounds/landing.png") no-repeat fixed
    center;
}

.landing .top {
  display: flex;
  align-items: flex-end;
}

.logo-title img {
  height: 200px;
}

.logo-title {
  font-size: 40px;
}

.title-wrapper {
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;

  font-weight: 500;
}

.title-wrapper span {
  height: 45px;
}

.landing-text {
  box-sizing: border-box;
  padding: 20px;
  font-weight: 100;
}

.landing-text span {
  font-size: 24px;
}

.landing-infos {
  color: white;
  margin-top: 50px;
}
</style>