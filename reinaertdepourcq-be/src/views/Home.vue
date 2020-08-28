<template>
  <div class="home">
    <Header />
    <div class="m-0">
      <div class="row m-0">
        <h2>This will be text</h2>
      </div>
      <div class="row m-0">
        <TextAnimation />
      </div>
    </div>
  </div>
</template>

<script>
import TextAnimation from "@/components/TextAnimation.vue";
export default {
  name: "Home",
  components: {
    TextAnimation,
  },
};
</script>
