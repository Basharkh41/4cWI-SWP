<template>
  <div>
    <button class="signs" @click="add">+</button>
    <button class="signs" @click="subtract">-</button>
    <button class="signs" @click="multi">*</button>
    <button class="signs" @click="divide">/</button>
    <button class="res" @click="result">=</button>
  </div>
</template>

<script>
export default {
  emits: [
    "number-add",
    "number-subtract",
    "number-multi",
    "number-divide",
    "result",
  ],
  components: {},
  data() {
    return {
    };
  },

  methods: {
    add() {
      this.$emit("number-add");
    },
    subtract() {
      this.$emit("number-subtract");
    },
    multi() {
      this.$emit("number-multi");
    },
    divide() {
      this.$emit("number-divide");
    },
    result() {
      this.$emit("result");
    },
  },
};
</script>

<style>
body {
  font-family: Georgia;
  background-color: black;
}
.signs {
  font-size: 20px;
  padding: 20px 50px 20px 50px;
  transition: 0.3s;
}

.res {
  font-size: 20px;
  padding: 20px 300px 20px 300px;
  margin-top: 1.5rem;
}

button {
  box-shadow: 5px 5px 10px rgb(83, 134, 83);
}
</style>
