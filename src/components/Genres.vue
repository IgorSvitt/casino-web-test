<script setup>

</script>

<template>
  <div class="genre1">
    <img src="@/assets/slot-machine.png" alt="">
    <span>Казино</span>
  </div>
  <div class="genre2">
    <img src="@/assets/diamonds.png" alt="">
    <span>Топ</span>
  </div>
  <div class="genre3">
    <img src="@/assets/casino-roulette.png" alt="">
    <span>Рулетка</span>
  </div>
  <div class="genre4">
    <img src="@/assets/dice.png" alt="">
    <span>Остальное</span>
  </div>
  <div class="genre5">
    <img src="@/assets/gift-box.png" alt="">
    <span>Бонус</span>
  </div>

</template>

<style scoped>
.genre1, .genre2, .genre3, .genre4, .genre5{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 10px;
  color: white;
  font-size: 20px;
  font-weight: 700;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
.genre1 {
  width: 170px;
  height: 170px;
  border-radius: 10px;
  background: linear-gradient(136deg, #7F7FD5 1.73%, #86A8E7 50.87%, #91EAE4 100%);
}

.genre2 {
  width: 170px;
  height: 170px;
  border-radius: 10px;
  background: linear-gradient(45deg, #F96 0%, rgba(255, 94, 98, 0.66) 97.65%);
}

.genre3 {
  width: 170px;
  height: 170px;
  border-radius: 10px;
  background: linear-gradient(314deg, #FFAFBD 7.64%, #FFC3A0 98.84%);
}

.genre4 {
  width: 170px;
  height: 170px;
  border-radius: 10px;
  background: linear-gradient(233deg, #EF32D9 13.29%, #89FFFD 97.06%);
}

.genre5 {
  width: 170px;
  height: 170px;
  border-radius: 10px;
  background: linear-gradient(266deg, #2F7336 3.57%, #AA3A38 97.44%);
}
img{
  width: 85px;
  height: 85px;
  flex-shrink: 0;
}
</style>