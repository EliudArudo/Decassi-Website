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
      <v-toolbar-side-icon class="hidden-md-and-up" @click="drawer = !drawer" />

      <v-toolbar-title v-text="title" />
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
      title: "Vuetify.js"
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

/* Unset any settings */
.container {
  max-width: unset;
}

.v-toolbar__content,
.body,
.footer-body {
  width: 100%;
  max-width: 1200px;
}

.v-content {
  align-items: flex-start;
}

.v-toolbar__content {
  background: rgba(0, 0, 0, 0.05);
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