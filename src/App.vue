<script setup>

  import { reactive, computed } from 'vue';

  import CompHeader from './components/CompHeader.vue'
  import CompForm from './components/CompForm.vue'
  import CompResult from './components/CompResult.vue'

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

  const updateNumber1 = (val) => {
    state.number1 = val
  }

  const updateNumber2 = (val) => {
    state.number2 = val
  }

  const updateOperation = (val) => {
    state.operation = val
  }  
</script>

<template>
  <div class="container">
    <CompHeader />
    <CompForm
      :number1="state.number1"
      :number2="state.number2"
      :operation="state.operation"
      @update:number1="updateNumber1"
      @update:number2="updateNumber2"
      @update:operation="updateOperation"
    />
    <CompResult :result="result"/>    
  </div>
</template>