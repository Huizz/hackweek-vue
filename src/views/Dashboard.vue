<template>
  <div>
    <Jio v-for="(jio, index) in jios" v-bind:jio="jio" v-bind:key="index"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Jio from '@/components/Jio.vue';

@Component({
  components: {
    Jio,
  },
  data() {
    return {
      jios: [
        {
          title: 'This is a jio',
          date: '2019-04-05',
        },
        {
          title: 'Daeyeol 보자',
          date: '2019-02-11',
        },
      ],
    };
  },
})
export default class Dashboard extends Vue {}
</script>

