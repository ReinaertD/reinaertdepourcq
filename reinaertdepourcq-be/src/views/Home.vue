<template>
  <div class="home">
    <Header />
    <div class="m-0">
      <div class="row m-0">
        <h2>This will be text</h2>
      </div>
      <div class="row m-0">
        <h1>Second Animation</h1>
      </div>
      <div class="row m-0">
        <TextAnimationv2 />
      </div>
    </div>
  </div>
</template>

<script>
// import TextAnimation from "@/components/TextAnimation.vue";
import TextAnimationv2 from "@/components/TextAnimationv2.vue";
export default {
  name: "Home",
  components: {
    // TextAnimation,
    TextAnimationv2,
  },
};
</script>
