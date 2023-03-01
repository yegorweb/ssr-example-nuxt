<script setup>
import { ref } from "vue-demi";
import MainForm from "../components/MainForm.vue";

let navigation_is_open = ref(false);

/* BASE:
	{
		route: '/',
		title: ''
	},
*/
let nav_buttons = [
  {
    route: "/",
    title: "Главная",
  },
  {
    route: "/mainForm",
    title: "Создать",
  },
  {
    route: "/blog",
    title: "Блог",
  },
  {
    route: "/delivery",
    title: "Доставка продуктов",
  },
  {
    route: "/aboutUs",
    title: "О нас",
  },
];
</script>


<template>
  <v-app>
    <!-- Header -->
    <v-app-bar color="primary" >
      <v-container>
        <v-row class="justify-space-between header-container align-center">
          <div><img style="height: 64px;" src="../assets/icons/logo.png"/></div>
          <div class="text-h6 header-title">ИнфоМама</div>
          <div>
            <v-icon
              @click="navigation_is_open = !navigation_is_open"
              icon="mdi-menu"
            ></v-icon>
          </div>
        </v-row>
      </v-container>
      <!-- <v-img height="100%" src="../assets/icons/logo.png"></v-img>
      <v-app-bar-title> ИнфоМама</v-app-bar-title>
      <v-icon
        @click="navigation_is_open = !navigation_is_open"
        icon="mdi-menu"
      ></v-icon> -->
    </v-app-bar>

    <!-- Панель навигации -->
    <v-navigation-drawer
      v-model="navigation_is_open"
      location="right"
      temporary
    >
      <v-list>
        <v-list-item v-for="(button, index) in nav_buttons" :key="index">
          <NuxtLink class="nav-list-item-link" :to="button.route">{{
            button.title
          }}</NuxtLink>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- Pages -->
    <v-main>
      <slot />
    </v-main>
    <v-footer color="primary" app class="text-center w-100">
      <div class="text-center w-100">
        {{ new Date().getFullYear() }} — <strong>Сделано в Кубит</strong>
      </div>
    </v-footer>
  </v-app>
</template>
	

<style lang="scss" scoped>
.nav-list-item-link {
  text-decoration: none;
  color: #000000;
}
.header-container {
  position: relative;
}
.header-title {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
