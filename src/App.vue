<script setup lang="ts">
  import { ref } from 'vue'

  import Hero from './components/Hero.vue'
  import Menu from './components/Menu.vue'
  import Story from './components/Story.vue'
  import Location from './components/Location.vue';

  const toggle_menu = ref("closed")

  const toggleMenu = () => {
    if (toggle_menu.value === "closed") {
      toggle_menu.value = "open"
    } else {
      toggle_menu.value = "closed"
    }

    console.log(toggle_menu.value)
  }
</script>

<template>
  <div class="announcement">Freshly brewed in Windhoek · Open daily</div>

  <header>
    <div class="container nav">
      <a class="logo" href="#">Kalahari <span>Coffee Co.</span></a>

      <button class="menu-toggle" @click="toggleMenu" aria-label="Toggle menu">☰</button>

      <nav :class="toggle_menu">
        <a href="#menu">Menu</a>
        <a href="#story">Our story</a>
        <a href="#visit">Visit us</a>
        <a class="nav-cta" href="#visit">Find the café</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <Hero />
    </section>

    <section class="menu-section" id="menu">
      <Menu />
    </section>

    <section id="story">
      <Story />
    </section>

    <section class="location" id="visit">
      <Location />
    </section>
  </main>

  <footer>
    <div class="container footer-inner">
      <span>© 2026 Kalahari Coffee Co.</span>
      <span>Made for Windhoek mornings.</span>
    </div>
  </footer>
</template>