<script setup>
import { ref, onMounted } from 'vue';

const skillsData = ref(null);

onMounted(async () => {
  const response = await import('@/assets/data/skills-section.json');
  skillsData.value = response.default;
});
</script>

<template>
  <aside v-if="skillsData"
    class="resume-aside col-12 col-lg-4 col-xl-3 px-lg-4 pb-lg-4"
  >
    <section class="skills-section py-3">
      <h3 class="text-uppercase resume-section-heading mb-4">
        Skills
      </h3>
      <div class="item mb-2">
        <h4 class="item-title">Technical</h4>
        <div class="skills-list">
          <p class="mb-2 skills-list-item" v-for="skill in skillsData?.technical" :key="skill">
            {{ skill }}
          </p>
        </div>
      </div>
      <div class="item">
        <h4 class="item-title">Professional</h4>
        <ul class="list-unstyled resume-skills-list">
          <li class="mb-2" v-for="skill in skillsData?.professional" :key="skill">
            {{ skill }}
          </li>
        </ul>
      </div>
      <div class="item">
        <h4 class="item-title">Expertise</h4>
        <ul class="list-unstyled resume-skills-list">
          <li class="mb-2" v-for="skill in skillsData?.additional" :key="skill">
            {{ skill }}
          </li>
        </ul>
      </div>
    </section>
  </aside>
</template>

<style scoped>
.skills-list {
  align-items: center;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;

  .skills-list-item {
    background-color: var(--bs-primary);
    border-radius: 4px;
    color: #ffffff;
    font-weight: bold;
    padding: 1px 4px;
  }
}
</style>
