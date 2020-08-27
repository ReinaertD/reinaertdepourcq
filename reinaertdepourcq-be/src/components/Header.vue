<template>
  <div class="nav-typo bg-light">
    <div class="nav justify-content-between">
      <div class="p-2 d-flex align-items-center">
        <router-link to="/">
          <span class="logo">Reinaert</span><br />
          <span class="logo">Depourcq</span>
        </router-link>
      </div>
      <ul class="nav p-2 align-items-center">
        <li class="nav-item">
          <router-link class="nav-link" to="/projects">Projects</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/random">Random</router-link>
        </li>
      </ul>
      <div class="nav">
        <span class="nav-icon p-2 px-3">
          <a class="fas fa-at" href="mailto:reinaert.depourcq@gmail.com"></a>
        </span>
        <span class="nav-icon nav-icon-alt p-2 px-3">
          <a
            class="fab fa-github nav-icon-alt-link"
            href="https://www.github.com"
          ></a>
        </span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Header",
};
</script>
<style scoped>
a {
  text-decoration: none;
  color: black;
}
.nav-typo {
  font-family: Alata;
}
.nav-icon {
  font-size: 3em;
}
.nav-icon-alt-link {
  color: white;
}
.nav-icon-alt {
  background-color: black;
}
.logo {
  font-weight: 800;
}
</style>
