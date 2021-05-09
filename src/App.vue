<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <p>Operand1 in parent is {{ operand1 }}</p>
  <button @click="resetOperand1">Reset</button>

  <multiply :operand1="operand1" @multi-by="multiBy" />
</template>

<script >
import { ref, computed } from "vue";
import Multiply from "./components/Multiply.vue";

export default {
  components: {
    Multiply,
  },
  setup() {
    let operand1 = ref(1); // ref

    const multiBy = (op) => {
      console.log(op);
      operand1.value *= op;
    };

    const resetOperand1 = () => {
      operand1.value = 1;
    };

    return {
      operand1,
      multiBy,
      resetOperand1
    };
  },
};

// import Multiply from "./components/Multiply.vue";

// export default {
//   components: {
//     Multiply,
//   },
//   data() {
//     return {
//       operand1: 1,
//     };
//   },
//   methods: {
//     multiBy(op) {
//       console.log(this.operand1);
//       this.operand1 *= op;
//     },
//     resetOperand1() {
//       this.operand1 = 1;
//     },
//   },
// };
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: burlywood;
}
</style>
