<template>
  <card>
    <template v-slot:card-header>
      <h1>Name: {{ name == "olay" ? "Bounphone" : name }}</h1>
    </template>

    <template v-slot:card-content>
      <p>Salary: {{ salary }}, Department : {{ department }}</p>
    </template>
  </card>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Person",
  props: {
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      default: 10000,
    },
    department: {
      type: String,
      default: "none",
    },
  },
  components: {
    Card,
  },
};
</script>

<style scoped>
h1 {
  color: black;
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
