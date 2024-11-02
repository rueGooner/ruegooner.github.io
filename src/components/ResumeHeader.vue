<script setup>
import { ref, onMounted } from 'vue';
import { Icon } from '@iconify/vue';

const headerData = ref(null);

onMounted(async () => {
  const response = await import('@/assets/data/header.json');
  headerData.value = response.default;
});
</script>

<template>
  <div class="resume-header" v-if="headerData">
    <div class="row align-items-center">
      <div class="resume-title col-12 col-md-6 col-lg-8 col-xl-9">
        <h2 class="resume-name mb-0 text-uppercase">
          {{ headerData.name }}
        </h2>
        <div class="resume-tagline mb-3 mb-md-0">
          {{  headerData.tagline }}
        </div>
      </div>
      <!--//resume-title-->
      <div class="resume-contact col-12 col-md-6 col-lg-4 col-xl-3">
        <ul class="list-unstyled mb-0">
          <li class="mb-2 h6" v-for="(contact, index) in headerData.contact" :key="index">
            <Icon :icon="contact.icon" class="h6 mb-1 me-2 link-primary" />
            {{ contact.text }}
          </li>
        </ul>
      </div>
      <!--//resume-contact-->
    </div>
    <!--//row-->
  </div>
</template>

<style scoped>
.resume-contact li {
  font-weight: unset;
}
</style>
