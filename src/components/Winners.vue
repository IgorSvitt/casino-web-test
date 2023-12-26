<script setup>
import { ref, onMounted } from 'vue';

const winnersData = ref([]);

onMounted(() => {
  generateWinnersData();
});

const generateWinnersData = () => {
  for (let i = 0; i < 7; i++) {
    const gradient = generateRandomGradient();
    const sum = generateRandomSum();
    const time = generateRandomTime();

    winnersData.value.push({
      gradient,
      sum,
      time,
      isActive: i % 2 === 0,
    });
  }
};

const generateRandomGradient = () => {
  const colors = [
    getRandomColor(),
    getRandomColor(),
  ];

  const gradientDirection = Math.random() * 360; // Угол направления градиента

  const gradient = `linear-gradient(${gradientDirection}deg, ${colors[0]}, ${colors[1]})`;

  return gradient;
};

const getRandomColor = () => {
  const letters = '0123456789ABCDEF';
  let color = '#';

  for (let i = 0; i < 6; i++) {
    color += letters[Math.floor(Math.random() * 16)];
  }

  return color;
};


const generateRandomSum = () => {
  return Math.floor(Math.random() * (400 - 100 + 1) + 100);
};

const generateRandomTime = () => {
  const now = new Date();
  const randomMinutes = Math.floor(Math.random() * 60);
  const newTime = new Date(now.getTime() - randomMinutes * 60000);
  return `${newTime.getHours()}:${String(newTime.getMinutes()).padStart(2, '0')}`;
};
</script>


<template>
  <div class="winners">
    <div class="title">
      <span>Выигрыши</span>
    </div>
    <div v-for="(winner, index) in winnersData" :key="index">
      <div class="winners__item" :class="{'active': winner.isActive}">
        <div class="winners__item__title" :style="{ background: winner.gradient }">
        </div>
        <div class="winners__item__time">
          <span>{{ winner.time }}</span>
        </div>
        <div class="winners__item__sum">
          <span>{{ winner.sum }}$</span>
        </div>
      </div>
    </div>
  </div>
</template>


<style scoped>
.winners{
  height: 397px;
  width: 100%;
  background-color: #4C3575;
  border-radius: 10px;
  font-size: 18px;

}
.title{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 40px;
  width: 100%;
  color: #fff;
  font-size: 24px;
  border-bottom: 1px solid #fff;
}

.winners__item{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  height: 50px;
  width: 100%;
  color: #fff;
  padding: 20px;
  border-radius: 10px;
}

.winners__item__title{
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background: rgb(38,90,99);
  background: linear-gradient(180deg, rgba(38,90,99,1) 0%, rgba(0,196,229,1) 100%);
}

.winners__item__time{
  color: rgba(255, 255, 255, 0.5);
  font-size: 15px;
}

.active{
  background: #7858A6;
}
</style>