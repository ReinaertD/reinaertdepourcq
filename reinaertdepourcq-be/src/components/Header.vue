<template>
  <div id="nav" class="navbar navbar-light">
    <ul class="nav">
      <li class="nav-item">
        <router-link class="nav-link" to="/">Home</router-link>
      </li>
      <li class="nav-item">
        <router-link class="nav-link" to="/projects">Projects</router-link>
      </li>
      <li class="nav-item">
        <router-link class="nav-link" to="/random">Random</router-link>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "Header",
};
</script>
