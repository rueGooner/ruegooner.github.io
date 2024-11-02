<script setup>
import { defineProps } from 'vue';

defineProps({
  techStack: Array
});

</script>

<template>
  <div class="sub-header">
    <p class="item">Tech Stack</p>
    <p class="item">
      {{
         techStack.join(', ')
      }}
    </p>
  </div>
</template>
