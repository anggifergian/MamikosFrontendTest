<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
  <div class="about">
    <div>
      <h1>This is an about page</h1>
  
      <nav>
        <RouterLink to="/">Go to Home</RouterLink>
      </nav>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
