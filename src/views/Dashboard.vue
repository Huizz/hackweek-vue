<template>
  <Jio v-bind:jio='jio'/>
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
      jio: {
        title: 'This is a jio',
        date: '2019-04-05',
      },
    };
  },
})
export default class Dashboard extends Vue {}
</script>

