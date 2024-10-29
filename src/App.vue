<template>
  <div class="container px-3 px-lg-5">
    <div class="resume-wrapper mx-auto theme-bg-light p-5 mb-5 my-5 shadow-lg">
      <ResumeHeader />
      <hr/>
      <ResumeIntro />
    </div>
  </div>
</template>

<script>
import ResumeHeader from "@/components/ResumeHeader.vue";
import ResumeIntro from "@/components/ResumeIntro.vue";

export default {
  name: 'App',
  components: {
    ResumeIntro,
    ResumeHeader,
  }
}
</script>
