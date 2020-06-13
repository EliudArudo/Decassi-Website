<template>
  <v-app>
    <!-- Side menu -->
    <v-navigation-drawer class="hidden-md-and-up" clipped v-model="drawer" fixed app>
      <v-list>
        <v-list-tile v-for="(item, i) in items" :to="item.to" :key="i" router exact>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <!-- Toolbar -->
    <v-toolbar clipped-left fixed app class="flex-center">
      <!-- Menu button -->
      <!-- <v-toolbar-side-icon class="hidden-md-and-up" @click="drawer = !drawer" /> -->

      <div class="middle-background blue-middle-background">&nbsp;</div>

      <div class="toolbar-content">
        <div class="flex-center logo-container">
          <img src="@/assets/img/logo.svg" alt="Logo" />
        </div>

        <div class="flex-center nav-items-container">
          <span class="toolbar-title">DeCassi Foundation</span>

          <div class="flex-center toolbar-items">
            <v-btn
              dark
              flat
              v-for="(button, index) of navButtons"
              :key="`nav-${index}`"
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
    <v-footer class="flex-center">
      <div class="full-size footer-body">
        <span>&copy; 2017</span>
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

      // New
      navButtons: [
        {
          title: "Home"
        },
        {
          title: "Services"
        },
        {
          title: "About us"
        },
        {
          title: "Contact us"
        }
      ]
    };
  }
};
</script>


<style>
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
}

.light-blue-text {
  color: #33b4e3;
}

.dark-blue-text {
  color: #112e84;
}

/* Common settings */
.paragraph {
  width: 245px;
  text-align: center;
  justify-content: flex-start;
  flex-direction: column;
  min-height: 170px;
  margin: 20px;
  font-weight: 500;
}

.small-paragraph {
  width: 130px;
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
  background: rgba(0, 0, 0, 0.03);
  padding-top: 0;
}

.footer-body {
  background: rgba(0, 0, 0, 0.05);
}

.v-footer {
  height: 230px !important;
  min-height: unset;
}
</style>