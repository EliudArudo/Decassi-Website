<template>
  <v-app>
    <!-- Side menu -->
    <v-navigation-drawer class="flex-center hidden-md-and-up" clipped v-model="drawer" fixed app>
      <v-list>
        <v-list-tile
          v-for="(item, index) in navButtons"
          @click="processNavItem(item)"
          :key="`menu-nav-item-${index}`"
        >
          <v-list-tile-content>
            <v-list-tile-title class="primary--text" v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <!-- Toolbar -->
    <v-toolbar clipped-left fixed app class="flex-center">
      <div class="middle-background blue-middle-background">&nbsp;</div>

      <div class="toolbar-content">
        <div class="flex-center logo-container">
          <img src="@/assets/img/logo.svg" alt="Logo" />
        </div>

        <div class="flex-center nav-items-container">
          <span class="toolbar-title">DeCassi Foundation</span>

          <div class="hidden-md-and-up">
            <v-toolbar-side-icon dark @click="drawer = !drawer" />
          </div>

          <div class="flex-center hidden-sm-and-down toolbar-items">
            <v-btn
              dark
              flat
              v-for="(button, index) of navButtons"
              :key="`nav-${index}`"
              @click="processNavItem(button)"
            >{{button.title}}</v-btn>
          </div>
        </div>
      </div>
    </v-toolbar>

    <!-- Website content -->
    <v-content class="flex-center">
      <v-container class="body">
        <nuxt />
      </v-container>
    </v-content>

    <!-- Footer -->
    <v-footer class="flex-center" id="footer">
      <div class="full-size flex-center footer-body">
        <div class="footer-item logo-info">
          <div class="flex-center top">
            <img src="@/assets/img/logo.svg" alt="Logo" />

            <div class="dark-blue-text logo-words">
              <span class="title-fix">
                De
                <span class="light-blue-text">Cassi</span>
              </span>
              <span>Foundation</span>
            </div>
          </div>

          <div class="flex-center primary--text bottom">
            <span>Dream</span>
            <span>|</span>
            <span>Believe</span>
            <span>|</span>
            <span>Achieve</span>
          </div>
        </div>

        <div class="footer-item flex-center nav-links">
          <v-btn
            color="primary"
            flat
            :ripple="false"
            v-for="(button, index) of navButtons"
            :key="`nav-${index}`"
            @click="processNavItem(button)"
          >{{button.title}}</v-btn>
        </div>

        <div class="footer-item flex-center light-blue-text location">
          <span class="flex-center flex-column location-details">
            <!-- Decassi Foundation -->
            <span class="dark-blue-text company-name">
              <span class="title-fix">
                De
                <span class="light-blue-text">Cassi</span>
              </span>
              <span>Foundation</span>
            </span>

            <!-- Another -->
            <span>114 New Edition Court</span>
            <span>Cary, NC 27511</span>
            <span>USA</span>
          </span>

          <span>decassi@email.com</span>

          <span class="copyright-message">Copyright 2020</span>
        </div>
      </div>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        { icon: "apps", title: "Home", to: "/" },
        { icon: "bubble_chart", title: "About", to: "/about" }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js",

      options: {
        duration: 2000,
        offset: 0,
        easing: "easeInOutCubic"
      },

      // New
      navButtons: [
        {
          title: "Home",
          path: "/"
        },
        {
          title: "About us",
          path: "/about"
        },
        {
          title: "Contact us",
          componentID: "footer"
        }
      ]
    };
  },
  watch: {
    $route: {
      handler: function(to, from) {
        const serviceRoute = {
          title: "Services",
          componentID: "services"
        };

        if (to.name === "about")
          this.navButtons = this.navButtons.filter(
            button => button.title !== "Services"
          );
        else this.navButtons.splice(1, 0, serviceRoute);
      },
      immediate: true
    }
  },
  methods: {
    processNavItem: function(button) {
      if (this.drawer) this.drawer = false;

      if (button.hasOwnProperty("path")) this.$router.push(button.path);
      else if (button.hasOwnProperty("componentID")) {
        const target = document.getElementById(button.componentID);

        this.$vuetify.goTo(target, this.options);
      }

      if (this.$route.path === "/" && button.title === "Home")
        this.slideToLandingPage();
    },
    slideToLandingPage() {
      const target = document.getElementById("landing");

      this.$vuetify.goTo(target, this.options);
    }
  }
};
</script>


<style>
::-webkit-scrollbar {
  width: 12px;
}
::-webkit-scrollbar-track {
  background: #fcfcfc;
}
::-webkit-scrollbar-thumb {
  background-color: #33b4e3;
  border-radius: 20px;
  border: 3px solid white;
}

/* Helpers */
.full-size {
  height: 100% !important;
  width: 100% !important;
}

.full-height {
  height: 100%;
}

.full-width {
  width: 100%;
}

.flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.flex-column {
  flex-direction: column;
}

.flex-row {
  flex-direction: row;
}

.text-center {
  text-align: center;
}

.full-opacity {
  opacity: 0.9 !important;
}

.full-color {
  color: rgba(255, 255, 255, 0.9);
}

body {
  font-family: "Open Sans";
  background: #fcfcfc;

  color: #051443;
  cursor: default;
  user-select: none;
}

.light-blue-text {
  color: #33b4e3;
}

.dark-blue-text {
  color: #112e84;
}

/* Common settings */
.paragraph {
  max-width: 245px;
  text-align: center;
  justify-content: flex-start;
  flex-direction: column;
  min-height: 170px;
  margin: 20px;
  font-weight: 500;
}

.small-paragraph {
  max-width: 130px;
  text-align: center;
  justify-content: flex-start;
  align-items: baseline;
  min-height: 130px;
  margin: 10px;
  font-weight: 500;
}

.section-title {
  height: 60px;
  font-size: 22px;
  font-weight: 600;
}

.section-icon {
  font-size: 40px;
  margin-bottom: 10px;
}

.section-card {
  box-shadow: -1px 0px 2px 6px rgba(0, 0, 0, 0.02);
}

.title-fix {
  display: inline-flex;
}

/* Unset any settings */
.container {
  max-width: unset;
}

.v-toolbar {
  background-color: #fcfcfc;
  height: 40px;
}

.v-toolbar__content,
.body,
.footer-body {
  width: 100%;
  max-width: 1200px;
}

.v-content {
  align-items: flex-start;
  padding: 40px 0px 0px !important;
}

.v-toolbar__content {
  /* background: rgba(0, 0, 0, 0.05); */
  height: 40px !important;
}

.middle-background {
  position: absolute;
  height: 100%;
  width: 50%;
}

.blue-middle-background {
  background-color: #33b4e3;
  right: 0;
}

.toolbar-content {
  height: 100%;
  width: 100%;

  display: flex;

  /* background: rgba(0, 0, 0, 0.03); */
  z-index: 1;
}

.logo-container {
  height: 100%;
  width: 64px;

  /* background: rgba(0, 0, 0, 0.05); */

  box-sizing: border-box;
  padding: 3px;
}

.logo-container img {
  height: 100%;
}

.nav-items-container {
  height: 100%;
  width: calc(100% - 40px);

  color: white;
  background: #33b4e3;
  justify-content: space-between;

  padding: 5px;
}

.toolbar-items .v-btn {
  text-transform: capitalize;
}

.body {
  /* background: rgba(0, 0, 0, 0.03); */
  padding-top: 0;
}

.footer-body {
  height: 100%;
  align-items: flex-start;
  flex-wrap: wrap;
  padding: 30px;
  justify-content: space-between;
}

.v-footer {
  height: unset !important;
  min-height: 230px !important;
  min-height: unset;
  background: #fcfcfc;

  box-shadow: 0px -1px 10px rgba(0, 0, 0, 0.2);
}

.logo-info {
  width: 170px;
}

.logo-info .top {
  height: 60px;
}

.logo-info .top img {
  width: 60px;
}

.logo-info .top .logo-words {
  width: calc(100% - 60px);
  font-size: 20px;
  font-weight: 500;
}

.logo-info .top .logo-words {
  line-height: 1.2;
}

.logo-info .bottom {
  justify-content: space-between;
}

.nav-links {
  flex-direction: column;
  align-items: flex-start;
  padding: 0 10px;
}

.nav-links .v-btn {
  padding: 0;
  height: 25px;
  text-transform: none;
  font-weight: 200;
  margin: 0;
}

.nav-links .v-btn .v-btn__content {
  justify-content: flex-start;
}

.v-navigation-drawer {
  width: 110px !important;
}

.v-navigation-drawer .v-list {
  width: 100%;
}

.location {
  align-items: flex-end;
  justify-content: space-between;
  flex-direction: column;
  height: 140px;
}

.location-details {
  align-items: flex-end;
}

.company-name {
  font-weight: 500;
}

.copyright-message {
  font-size: 10px;
}

@media only screen and (max-width: 520px) {
  .footer-body {
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .footer-body .footer-item {
    margin-bottom: 20px;
  }

  .section-title {
    text-align: center;
    min-height: 60px;
  }

  .footer-body .nav-links .v-btn .v-btn__content {
    justify-content: center;
  }

  .footer-body .location {
    align-items: center;
  }

  .footer-body .location-details {
    align-items: center;
  }
}

/* * {
  border: 1px solid #f00 !important;
} */

/* Animations */
.animated {
  transition: all 0.4s ease-in-out;
}

.animated:hover {
  transform: scale(1.1);
}
</style>