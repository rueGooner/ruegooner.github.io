<script setup>
import {ref, onMounted} from 'vue';

const introduction = ref(null);

onMounted(async () => {
  const response = await import('@/assets/data/introduction.json');
  introduction.value = response.default;
});
</script>

<template>
  <div class="resume-intro py-3" v-if="introduction">
    <div class="row align-items-center">
      <div class="col-12 col-md-3 col-xl-2 text-center">
        <img
          class="resume-profile-image mb-3 mb-md-0 me-md-5 ms-md-0 rounded mx-auto"
          src="../assets/me.png"
          alt="image"
        />
      </div>


      <div class="col text-start">
        <p class="mb-1">{{ introduction?.summary }}</p>
        <p>{{ introduction?.leadership }}</p>
      </div>
      <!--//col-->
    </div>
  </div>
</template>
