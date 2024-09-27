<template>
  <v-app>
    <v-card>
      <v-layout>
        <v-app-bar color="black" prominent>
          <v-app-bar-nav-icon
            variant="text"
            @click.stop="drawer = !drawer"
          ></v-app-bar-nav-icon>
          <v-img class="mx-2" src="./assets/label-white.png" max-height="64px" max-width="200px"/>
        </v-app-bar>

        <v-navigation-drawer
          v-model="drawer"
          :location="$vuetify.display.mobile ? 'bottom' : undefined"
          temporary
        >
          <v-list :items="items"></v-list>
        </v-navigation-drawer>
        
        <v-main style=" background: linear-gradient(90deg, rgba(2,0,36,1) 22%, rgba(17,147,47,1) 50%, rgba(115,46,103,1) 78%);">
          <router-view />
        </v-main>
      </v-layout>
    </v-card>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
    items: [
      {
        title: "Главная",
        value: "main",
      },
      {
        title: "Bar",
        value: "bar",
      },
      {
        title: "Fizz",
        value: "fizz",
      },
      {
        title: "Авторизация",
        value: "auth",
      },
    ],
  }),

  watch: {
    group() {
      this.drawer = false;
    },
  },
};
</script>
