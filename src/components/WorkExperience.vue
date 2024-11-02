<script setup>
import {onMounted, ref} from "vue";
import SubHeading from "@/components/SubHeading.vue";
import ItemHeading from "@/components/ItemHeading.vue";

const workExperience = ref(null);

onMounted(async () => {
  const response = await import('@/assets/data/work-experience.json');
  workExperience.value = response.default;
});
</script>

<template>
  <section v-if="workExperience" class="work-section py-3">
    <h3 class="text-uppercase resume-section-heading mb-4">Work Experience</h3>
    <div class="item mb-3" v-for="(experience, experienceIndex) in workExperience" :key="experienceIndex">
      <ItemHeading
        :position="experience.position"
        :company="experience.company"
        :dates="experience.dates"
      />
      <SubHeading :tech-stack="experience.techStack" />
      <div class="item-content">
        <p class="">{{ experience.companyDescription }}</p>
        <p>{{ experience.jobRole }}</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.item-content > p:first-child {
  font-weight: bold;
}
</style>
