<script setup>

</script>

<template>
  <div class="left">
    <div>
      <img src="@/assets/o8819tfg%201.png " alt="logo" class="left__menu__logo">
    </div>
    <div class="menu__title">Меню</div>
    <div class="left__menu">
      <div class="left__menu__item choose">
        <img src="@/assets/home.svg" alt="logo" class="left__menu__item__logo">
        <span>Главная</span>
      </div>
      <div class="left__menu__item">
        <img src="@/assets/dice-alt.svg" alt="logo" class="left__menu__item__logo">
        <span>Игры</span>
      </div>
      <div class="left__menu__item">
        <img src="@/assets/trophy.svg" alt="logo" class="left__menu__item__logo">
        <span>Турниры</span>
      </div>
      <div class="left__menu__item">
        <img src="@/assets/users.svg" alt="logo" class="left__menu__item__logo">
        <span>Поддержка</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.left {
  height: 594px;
  width: 173px;
  background-color: #4C3575;
  border-radius: 10px;
  padding: 20px 10px;
  color: #ffffff;
}
.left__menu{
  display: flex;
  flex-direction: column;
  align-items: start;
}
.left__menu__item {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 10px;
  padding: 5px 10px;
  border-radius: 10px;
  cursor: pointer;

}

.menu__title{
  font-size: 20px;
  font-weight: 400;
  margin-top: 20px;
  display: flex;
  justify-content: center;
}

.choose{
  width: 153px;
  background: rgb(245,136,64);
  background: linear-gradient(163deg, rgba(245,136,64,1) 38%, rgba(245,227,64,1) 100%);
}
</style>