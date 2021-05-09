<template>
  <div>Child component</div>
  <div>

    (Recieved fm parent {{ operand1 }}) X
    <input type="text" placeholder="Enter a num" v-model="operand2" />

    <button @click.prevent="$emit('multi-by', operand2)">Multiply</button>
  </div>
</template>

<script >
import { ref } from "vue";
export default {
  props: {
    operand1: Number,
  },
  emits: ["multi-by"],// look like angular @output

  setup() {
    const operand2 = ref(0);
    return {
      operand2,
    };
  },
};

// export default {
//   props: {
//     operand1: Number,
//   },
//     emits: ["multi-by"],// look like angular @output
//   data() {
//     const operand2 = 0;
//     return {
//       operand2,
//     };
//   },

// };
</script>

<style scoped>
div {
  background-color: #97e8ee;
}
</style>
