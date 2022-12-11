<template>
  <div class="parent">
    <h1>Calculator</h1>
    <input type="text" class="inputCalc" v-model="numberFromInput" />
      <simple-button class="buttons"
        @number-add="add"
        @number-subtract="subtract"
        @number-multi="multi"
        @number-divide="divide"
        @result="result"
      ></simple-button>
  </div>
</template>
<script>
import SimpleButton from "./SimpleButton.vue";

export default {
  emits: ["resultNumber"],
  name: "App",
  props: {
  },
  components: {
    SimpleButton,
  },
  data() {
    return {
      numberFromInput: '',
      operator: "",
      resultNumber: 0,
    };
  },
  methods: {
    add() {
      this.numberFirst = this.numberFromInput;
      this.operator = "+";
      this.numberFromInput = '';
    },
    subtract() {
      this.numberFirst = this.numberFromInput;
      this.operator = "-";
      this.numberFromInput = '';
    },
    multi() {
      this.numberFirst = this.numberFromInput;
      this.operator = "*";
      this.numberFromInput = '';
    },
    divide() {
      this.numberFirst = this.numberFromInput;
      this.operator = "/";
      this.numberFromInput = '';
    },
    result() {
      this.numberSecond = this.numberFromInput;
      switch (this.operator) {
        case "+":
          this.resultNumber =
            parseInt(this.numberFirst) + parseInt(this.numberSecond);
            this.numberFromInput = this.resultNumber
          break;
        case "-":
          this.resultNumber =
            parseInt(this.numberFirst) - parseInt(this.numberSecond);
            this.numberFromInput = this.resultNumber
          break;
        case "*":
          this.resultNumber =
            parseInt(this.numberFirst) * parseInt(this.numberSecond);
            this.numberFromInput = this.resultNumber
          break;
        case "/":
          this.resultNumber =
            parseInt(this.numberFirst) / parseInt(this.numberSecond);
            this.numberFromInput = this.resultNumber
          break;
      }
    },
  },
};
</script>
<style>
.buttons {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
.parent {
    background-color: rgb(20, 107, 20);
  border-radius: 30px;
  padding: 2em 1em 12em 1em;
  margin: auto;
  width: 292px;
  clear: both;
  display: table;
}
.inputCalc {
  text-align: center;
  height: 50px;
  width: 610px;
  margin-bottom: 1rem;
  font-size: 30px;
}
h1 {
  font-size: 4rem;
}
</style>
