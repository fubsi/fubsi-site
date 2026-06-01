<script setup>
import './assets/agency.css'
import './assets/objects.css'
import AppSidebar from './components/AppSidebar.vue'
import AppNav from './components/AppNav.vue'
</script>

<template>
  <div class="bg-grid">
    <div class="line"></div><div class="line"></div>
    <div class="line"></div><div class="line"></div>
    <div class="line"></div>
  </div>

  <AppSidebar />

  <main class="main-content">
    <AppNav />
    
    <router-view v-slot="{ Component }">
        <transition name="page-slide" mode="out-in">
            <component :is="Component" />
        </transition>
    </router-view>
    
  </main>
</template>

<style scoped>
/* Nur noch das Layout-CSS bleibt hier */
.main-content {
  margin-left: 0;
  padding-top: 70px;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

@media (min-width: 768px) {
  .main-content {
    margin-left: 100px;
    padding-top: 0;
  }
}

/* =========================================
   PAGE TRANSITIONS (Fade & Slide)
========================================= */

/* 1. Zustand WÄHREND die Seite reinkommt oder rausgeht (Dauer & Art der Animation) */
.page-slide-enter-active,
.page-slide-leave-active {
  transition: all 0.7s cubic-bezier(0.25, 0.8, 0.25, 1);
}

/* 2. Start-Zustand der NEUEN Seite (bevor sie reinkommt) & End-Zustand der ALTEN Seite (wenn sie weg ist) */
.page-slide-enter-from,
.page-slide-leave-to {
  opacity: 0;
  transform: translateX(160px); /* Startet/Endet 60px weiter rechts */
}

/* 3. (Optional) Normalzustand der Seite (opacity: 1, transform: translateX(0)) 
   macht Vue automatisch, muss also nicht extra geschrieben werden. */
</style>