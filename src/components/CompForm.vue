<script setup>

  const props = defineProps({
    number1: Number,
    number2: Number,
    operation: String
  });

  const emits = defineEmits(['update:number1', 'update:number2', 'update:operation']);

</script>

<template>

  <form>
    <div class="row d-flex">
      <div class="col d-flex gap-4">
        <input type="number" :value="props.number1" @input="emits('update:number1', parseFloat($event.target.value))" placeholder="Enter your number first" class="form-control">
        <input type="number" :value="props.number2" @input="emits('update:number2', parseFloat($event.target.value))" placeholder="Enter your number second" class="form-control">
      </div>
      <div class="col-md-2">
        <select :value="props.operation" @change="emits('update:operation', $event.target.value)" class="form-control">            
          <option value="sum">Sum</option>
          <option value="subtraction">Subtraction</option>
          <option value="multiplication">Multiplication</option>
          <option value="division">Division</option>
        </select>
      </div>        
    </div>
  </form>
  
</template>

