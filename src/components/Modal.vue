<template>
  <v-dialog v-model="show" max-width="500px">
    <div class="font pointer" @click="show = !show">
      <v-card>
        <v-card-title class="justify-center">
          <h2>{ {{ titleValue }} }</h2>
        </v-card-title>
        <v-card-text v-html="bodyValue" />
      </v-card>
    </div>
  </v-dialog>
</template>
<script>
export default {
  name: "ModalComponent",
  props: {
    value: Boolean,
    title: String,
    body: String,
  },
  computed: {
    titleValue: {
      get() {
        return this.title;
      },
    },
    bodyValue: {
      get() {
        return this.body;
      },
    },
    show: {
      get() {
        return this.value;
      },
      set(value) {
        this.$emit("input", value);
      },
    },
  },
};
</script>
<style scoped>
.theme--light.v-sheet {
  background-color: #0f0b07;
  border-style: solid;
  border-color: #be884b;
  color: #d8d6cf;
}
center {
  align-content: center;
}
.pointer {
  cursor: pointer;
}
.v-card__text {
  color: #d8d6cf !important;
}
</style>
