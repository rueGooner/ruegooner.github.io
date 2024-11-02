<script setup>
import { defineProps } from 'vue';

defineProps({
  position: String,
  company: String,
  dates: String,
});
</script>

<template>
  <div class="item-heading row align-items-center mb-2">
    <h4 class="item-title col-12 col-md-6 col-lg-8 mb-2 mb-md-0">
      {{ position }}
    </h4>
    <h5 class="item-meta col-12 col-md-6 col-lg-4 text-muted text-start text-md-end display-2">
      {{ company }} | {{ dates }}
    </h5>
  </div>
</template>
