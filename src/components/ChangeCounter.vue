<template>
    <button @click="increa({value: 1})">Add 1</button>
    <button @click="inc">Add 2</button>
</template>

<script>
import { mapActions } from 'vuex';

export default {
  methods: {
    // addOne() {
    //   this.$store.commit('increase', {value: 1});
    // },
    // addTwo() {
    //   this.$store.dispatch('increment');
    // },
    // ...mapActions(['increment', 'increase'])
    ...mapActions({
      inc: 'numbers/increment',
      increa: 'numbers/increase'
    })
  }
}
</script>