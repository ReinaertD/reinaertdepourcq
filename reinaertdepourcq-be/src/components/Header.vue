<template>
  <div class="navigation-bar bg-light">
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
          <router-link class="nav-link" to="/random">Random</router-link>
        </li>
      </ul>
      <div class="">
        <span class="nav-icon nav-icon-alt-a">
          <a
            class="fas fa-at nav-icon-alt-a-link p-2 px-3"
            href="mailto:reinaert.depourcq@gmail.com"
          ></a>
        </span>
        <span class="nav-icon nav-icon-alt">
          <a
            class="fab fa-github nav-icon-alt-link p-2 px-3"
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
@media (max-width: 450px) {
  .nav-icon {
    display: none;
  }
}
a {
  text-decoration: none;
  color: black;
}
.nav-icon {
  font-size: 3em;
  line-height: 1;
}

.nav-link {
  font-size: 20px;
}
.navigation-bar {
  border-bottom: 3px solid darkslategrey;
}
/* .nav-icon-alt,
.nav-icon-alt-link,
.nav-icon-alt-a:hover,
.nav-icon-alt-a-link:hover {
  background-color: black;
  color: white;
}
.nav-icon-alt-link:hover,
.nav-icon-alt:hover,
.nav-icon-alt-a,
.nav-icon-alt-a-link {
  color: black;
  background-color: white;
} */
.logo {
  font-weight: 800;
}
</style>
