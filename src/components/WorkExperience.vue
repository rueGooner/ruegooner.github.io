<script setup>
import {onMounted, ref} from "vue";

const workExperience = ref(null);

onMounted(async () => {
  const response = await import('@/assets/data/work-experience.json');
  workExperience.value = response.default;
});

console.log('SOMETHING', workExperience.value)
</script>

<template>
  <section v-if="workExperience" class="work-section py-3">
    <h3 class="text-uppercase resume-section-heading mb-4">Work Experience</h3>
    <div class="item mb-3" v-for="(experience, experienceIndex) in workExperience" :key="experienceIndex">
      <div class="item-heading row align-items-center mb-2">
        <h4 class="item-title col-12 col-md-6 col-lg-8 mb-2 mb-md-0">
          {{ experience.position }}
        </h4>
        <h5 class="item-meta col-12 col-md-6 col-lg-4 text-muted text-start text-md-end display-2">
          {{ experience.company }} | {{ experience.dates }}
        </h5>
      </div>
    </div>
  </section>
</template>

