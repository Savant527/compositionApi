import UserRepositories from './components/UserRepositories.vue';

<template>
  <UserRepositories :user="'Diana'"></UserRepositories>
  <Home first-name="Sebastian" last-name="Navas" otro="algo"></Home>
</template>

<script>
import UserRepositories from "./components/UserRepositories.vue";
import Home from "@/components/Home.vue";
import { provide } from "vue";

export default {
  name: "App",
  components: {
    UserRepositories,
    Home,
  },
  setup() {
    provide("username", "Savant527");
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
