<script setup>

import WorkExperience from "@/components/WorkExperience.vue";
import ResumeFooter from "@/components/ResumeFooter.vue";
import ResumeSkills from "@/components/ResumeSkills.vue";
</script>

<template>
  <div class="resume-body">
    <div class="row">
      <div class="resume-main col-12 col-lg-8 col-xl-9 pe-0 pe-lg-5">
        <WorkExperience />
        <ResumeFooter />
        <!--//work-section-->
      </div>
      <!--//resume-main-->
      <ResumeSkills />
      <!--//resume-aside-->
    </div>
    <!--//row-->
  </div>
</template>

<style scoped>

</style>
