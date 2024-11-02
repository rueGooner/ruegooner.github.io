<script setup>
import { ref, onMounted } from 'vue';
import { Icon } from '@iconify/vue';

const footerData = ref(null);

onMounted(async () => {
  const response = await import('@/assets/data/footer.json');
  footerData.value = response.default;
});

</script>

<template>
  <hr/>
  <div class="resume-footer text-center">
    <ul
      class="resume-social-list list-inline mx-auto mb-0 d-inline-block"
    >
      <li class="list-inline-item mb-lg-0 me-3" v-for="(social, socialIndex) in footerData" :key="socialIndex">
        <a :href="social.href" class="resume-link" target="_blank">
          <Icon :icon="social.icon" class="me-2 h5 link-primary" />
          <span class="d-none d-lg-inline-block text-muted">
          {{ social.text }}
        </span>
        </a>
      </li>
    </ul>
  </div>
</template>

<style scoped>

</style>
