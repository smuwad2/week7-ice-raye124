<script>
    export default { 
        // Add Code Here to complete the task
        // Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!
        data() {
          return {
            x: 0,
            y: 0,
            operations: ['+', '-', '*', '/', '%'],
            selectedOp: '+' // Default option
          }
        },
        computed: {
            operators() {
              return this.operations; // return all the operators (use in for loop later)
            },
            result() {
              if (this.selectedOp === '+') {
                return this.x + this.y;
              }
              else if (this.selectedOp === '-') {
                return this.x - this.y;
              }
              else if (this.selectedOp === '*') {
                return this.x * this.y;
              }
              else if (this.selectedOp === '/') {
                if (this.y !== 0) {
                  return this.x / this.y;
                }
                else {
                  return "∞"; // division by zero;
                }
              }
              else if (this.selectedOp === "%") {
                if (this.y !== 0) {
                return this.x % this.y;
              }
              else {
                return "∞"; // division by zero;
              }
          }
          else {
            return "Error";
          }
          // Alternatively, consider this:
          // switch(this.selectedOp) {
            // case "+": return this.x + this.y;
            // case "-": return this.x - this.y;
            // case "*": return this.x * this.y;
            // case "/": return this.x / this.y;
            // case "%": return this.x % this.y;
          }
      }
    }
</script>

<template>
    <p>x<input v-model.number="x"></p>
    <select v-model="selectedOp"> <!-- Whatever operator you select, shows up here -->
        <option v-for="op in operations"> {{ op }}</option>
    </select>
    <p>y <input v-model.number="y"></p>
    
    <p>---------------------</p>
    <p> = {{ result }} </p>
</template>

<style scoped>
    p, input { font-family: monospace; }
    p { white-space: pre; }

</style>
