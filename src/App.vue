<script setup>
import { reactive, computed } from 'vue';

  const state = reactive({
    number1: '',
    number2: '',
    operation: 'sum',
  })

  const result = computed(() => {
    switch(state.operation) {
      case 'sum':
        return state.number1 + state.number2;
      case 'subtraction':
        return state.number1 - state.number2;
      case 'multiplication':
        return state.number1 * state.number2;
      case 'division':
        return state.number2 !== 0 ? state.number1 / state.number2 : 'Cannot divide by zero';
      default:
      return 0;  
    }
  })
  
</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 text-center bg-light rounded-3">
        <h1>arithmetic calculator</h1>
        <p>Do your calculation</p>
    </header>
    <form>
      <div class="row d-flex">
        <div class="col d-flex gap-2">
          <input type="number" v-model.number="state.number1" placeholder="Enter your number first" class="form-control">
          <input type="number" v-model.number="state.number2" placeholder="Enter your number second" class="form-control">
        </div>
        <div class="col-md-2">
          <select v-model="state.operation" class="form-control">            
            <option value="sum">Sum</option>
            <option value="subtraction">Subtraction</option>
            <option value="multiplication">Multiplication</option>
            <option value="division">Division</option>
          </select>
        </div>        
      </div>
    </form>    
    <ul class="list-group mt-4">
      <h2>Result</h2>
      <li class="list-group-item">
        <p class="result text-center"> {{ result }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped>

</style>
