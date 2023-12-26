<script setup>

import Header from "@/components/Header.vue";
import LeftMenu from "@/components/LeftMenu.vue";
import Main from "@/components/Main.vue";
</script>

<template>
  <div class="header">
    <Header class="header__item"/>
  </div>
  <main class="menu">
    <LeftMenu/>
    <Main/>
  </main>
</template>

<style scoped>
.header {
  background-color: #4C3575;
  height: 50px;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 100;
}

.menu {
  display: flex;
  flex-direction: row;
  margin-top: 70px;
  height: 100%;
  width: 100%;
  gap: 20px;
}
</style>
