<template>
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <div class="container-fluid ">
    <router-link :to="{name : 'Home'}" class="navbar-brand">API ANIME</router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarText" aria-controls="navbarText" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarText">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <router-link :to="{name: 'Home'}" aria-current="page" class="nav-link">Animes</router-link>
        </li>
        <li class="nav-item">
            <router-link :to="{name : 'Manga'}" class="nav-link">Manga</router-link>
        </li>
        <li class="nav-item">
            <router-link :to="{name : 'Characters'}" class="nav-link">Characters</router-link>
        </li>
        <li class="nav-item">
            <router-link :to="{name : 'About'}" class="nav-link">About</router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>    
</template>


<script>

</script>


<style lang="scss" scoped>

</style>
