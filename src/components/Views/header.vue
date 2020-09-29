<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg fixed-top">
        <router-link to="/" class="navbar-brand text-white" href="#">Erica</router-link>
        <button class="navbar-toggler bg-light" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav ml-auto">
            <li class="nav-item">
                <router-link to="/" class="nav-link text-white" href="#">Home <span class="sr-only">(current)</span></router-link>
            </li>
            <li class="nav-item">
                <router-link to="/app" class="nav-link text-white" href="#">Player</router-link>
            </li>
            <li class="nav-item">
                <!-- <router-link to="/" class="nav-link text-white" href="#">Our Team</router-link> -->
            </li>
            </ul>
        </div>
    </nav>
  </div>
</template>

<script>

export default {
  name: "",
  components: {},
};
</script>

<style scoped>
nav {
  background: linear-gradient(to bottom right,  #001a33, #ff66ff);
}
</style>