<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld v-bind:msg="msg" />
  </div>
</template>

<script lang="ts">
// use v-bind for dynamic data
// https://vuejs.org/v2/guide/components.html#Passing-Data-to-Child-Components-with-Props
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

@Component({
  components: {
    HelloWorld,
  },
  data() {
    return {
      msg: 'Welcome to Your Vue.js + TypeScript App',
    };
  }, // data should be a functiont that returns the value to the instance
})
export default class Home extends Vue {}
</script>
