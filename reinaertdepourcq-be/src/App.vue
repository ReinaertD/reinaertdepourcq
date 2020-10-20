<template>
  <div id="app" class="vh justify-content-between">
    <Header />
    <router-view />
    <Footer />
  </div>
</template>
<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
export default {
  name: "app",
  components: { Header, Footer },
};
</script>
<style>
.vh {
  height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>
