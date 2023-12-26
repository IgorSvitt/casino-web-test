<script setup>

import MainNews from "@/components/MainNews.vue";
import Winners from "@/components/Winners.vue";
import Genres from "@/components/Genres.vue";
import Games from "@/components/Games.vue";
</script>

<template>
  <div class="main__menu">
    <div class="top">
      <MainNews/>
      <Winners/>
    </div>
    <div class="genres">
      <Genres/>
    </div>
    <div class="games">
      <Games/>
    </div>
  </div>
</template>

<style scoped>
.main__menu{
  height: 100%;
  width: 83%;
}

.top{
  display: flex;
  justify-content: space-between;
  height: 100%;
  width: 100%;
  gap: 20px;
}

.genres{
  margin: 20px 0px;
  display: flex;
  justify-content: space-between;
  height: 100%;
  width: 100%;
  gap: 20px;
}
</style>