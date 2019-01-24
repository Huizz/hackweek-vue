<template>
  <div class="jio">
    <div class="jio__title">{{jio.title}}</div>
    <div class="jio__date">{{jio.date}}</div>
    <b-btn class="btn btn-info jio__btn" @click="show=true">Me!</b-btn>

    <b-modal v-model="show" id="joinJioModal" title="Add me to the jio">
      <div class="modal-body">
        <div class="input-group mb-3 flex-column">
          <input
            type="text"
            class="form-control mb-2 w-100"
            v-model="newPersonName"
            placeholder="Name"
            aria-label="Name"
          >
          <input
            type="text"
            class="form-control w-100"
            v-model="newPersonHandle"
            placeholder="Telegram handler"
            aria-label="Telegram-handler"
          >
        </div>
      </div>
      <div slot="modal-footer">
        <button type="button" class="btn btn-secondary mr-1" @click="show=false">Close</button>
        <button type="button" class="btn btn-primary" @click="handleAddPerson">Save changes</button>
      </div>
    </b-modal>
    <div v-for="(person, index) in persons" :key="index">{{person}}</div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Jio extends Vue {
  @Prop() private jio!: object;
  private data() {
    return {
      show: false,
      persons: [],
      newPersonName: '',
      newPersonHandle: '',
    };
  }

  private handleAddPerson() {
    if (this.$data.newPersonName === '' || this.$data.newPersonHandle === '') {
      alert('empty fields');
      return;
    }
    this.$data.persons.push({
      name: this.$data.newPersonName,
      handle: this.$data.newPersonHandle,
    });
    this.$data.show = false;
  }
}
</script>

<style lang="scss" scoped>
.jio {
  overflow: hidden;
  text-align: left;
  &__btn {
    float: right;
  }
}
</style>
