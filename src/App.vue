<template>
  <base-container title="Vuex" v-if="isAuth">
    <TheCounter></TheCounter>
    <button @click="addOne">Add 11</button>
    <button @click="addFive">Add 5</button>
    <ChangeCounter></ChangeCounter>
    <FavoriteValue></FavoriteValue>
  </base-container>
  <base-container title="Auth">
    <UserAuth></UserAuth>
  </base-container>
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import TheCounter from './components/TheCounter.vue';
import ChangeCounter from './components/ChangeCounter.vue';
import FavoriteValue from './components/FavoriteValue.vue';
import UserAuth from './components/UserAuth.vue';

export default {
  components: {
    BaseContainer,
    TheCounter,
    ChangeCounter,
    FavoriteValue,
    UserAuth
  },
  methods: {
    addOne() {
      this.$store.commit({
        type:'numbers/increase',
        value: 11
      });
    },
    addFive() {
      this.$store.dispatch({
        type:'numbers/increase',
        value: 5
      });
    }
  },
  computed: {
    isAuth() {
      return this.$store.getters.userIsAuthenticated;
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>