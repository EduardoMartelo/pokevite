<script setup>
import { ref } from 'vue'

let num = ref(0)
</script>

<template>
  <!-- navbar -->
  <nav class="navbar navbar-expand-lg navbar-light bg-menu">
    <div class="container-fluid">
      <RouterLink class="navbar-brand" to="#">
        <img src="https://cdn-icons-png.flaticon.com/512/188/188987.png" alt="logo" width="30" height="24" class="d-inline-block align-center">
        PokeVite
      </RouterLink>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
        aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/about">About</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <!-- content -->
  <div class="main">
    <RouterView>
      
    </RouterView>
  </div>
  <footer class="bg-primary text-light">
    <div>Design in {{ new Date().getFullYear() }}</div>
  </footer>
</template>

<style>
body {
  height: 100vh;
  background: rgb(53,172,221);
  background: linear-gradient(0deg, rgba(53,172,221,1) 0%, rgba(0,41,150,1) 100%);
}

footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 56px;
}

.bg-menu {
  background: rgb(72,63,251);
  background: radial-gradient(circle, rgba(72,63,251,0.8071613641456583) 0%, rgba(70,252,244,0.5102415966386555) 100%);
}
</style>