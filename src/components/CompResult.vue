<script setup>
  const props = defineProps({
    result: Number | String
  });
</script>

<template>

  <ul class="list-group mt-4">
    <h2 class="p-3 text-center text-dark text-opacity-25 bg-danger-subtle rounded-3 mb-4">Result</h2>
    <li class="list-group-item">
      <p class="result text-center p-3"> {{ props.result }}</p>
    </li>
  </ul> 
   
</template>
