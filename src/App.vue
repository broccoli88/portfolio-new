<script setup>
import { RouterView } from 'vue-router'
import NavBar from './components/NavBar.vue'
</script>

<template>
      <header>
            <NavBar />
      </header>
      <main>
            <RouterView />
      </main>
      <footer></footer>
</template>

<style lang="scss" scoped></style>
