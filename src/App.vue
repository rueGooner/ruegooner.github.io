<template>
  <div class="container px-3 px-lg-5">
    <div class="resume-wrapper mx-auto theme-bg-light p-5 mb-5 my-5 shadow-lg">
      <ResumeHeader />
    </div>
  </div>
</template>

<script>
import ResumeHeader from "@/components/ResumeHeader.vue";

export default {
  name: 'App',
  components: {
    ResumeHeader,
  }
}
</script>
