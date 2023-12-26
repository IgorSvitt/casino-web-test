<script setup>

</script>

<template>
  <div class="games__header">
    <div class="title">
      Топ игр
    </div>
    <div class="game_btn">
      <span>Все игры</span>
    </div>
  </div>
  <div class="games">
    <div class="game">
      <img src="@/assets/2qojq9uv%201.svg" />
    </div>
    <div class="game">
      <img src="@/assets/z6p2r4sm%201.svg" />
    </div>
    <div class="game">
      <img src="@/assets/q3v5ev2w%201.svg" />
    </div>
    <div class="game">
      <img src="@/assets/sqd505sz%201.svg" />
    </div>
    <div class="game">
      <img src="@/assets/c3tovk9l%201.svg" />
    </div>
    <div class="game">
      <img src="@/assets/flu28obl%201.svg" />
    </div>
  </div>

</template>

<style scoped>
  .games__header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 40px 0;
    color: #fff;
  }
  .title{
    font-size: 28px;
    font-weight: 600;
  }
  .game_btn{
    width: 156px;
    height: 45px;
    border-radius: 10px;
    background: rgb(245,136,64);
    background: linear-gradient(163deg, rgba(245,136,64,1) 38%, rgba(245,227,64,1) 100%);
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    font-size: 20px;
  }
  .games{
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
  }
  .game{
    border-radius: 10px;
  }
</style>