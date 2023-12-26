<script setup>

</script>

<template>
  <header>
    <div class="navbar">
      <div class="navbar__item title">
        <img src="@/assets/chip.png" alt="" class="logo">
        Fade Casino
      </div>
      <div class="navbar__item">
        <div class="choose">
          Главная
        </div>
        <div>
          Игры
        </div>
        <div>
          Турниры
        </div>
      </div>
      <div class="navbar__item">
        <div class="search">
          <img src="@/assets/free-icon-font-search-3917132.svg" />
          <span class="line__search"></span>
          <input type="text" placeholder="Поиск">
        </div>
        <div class="balance">
          234$
          <img src="@/assets/usdt-svgrepo-com.svg">
        </div>
        <div class="account">

        </div>
      </div>

    </div>
  </header>
</template>

<style scoped>
.title{
  font-size: 25px;
  font-weight: 600;
}
.navbar {
  margin: auto;
  max-width: 1140px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 0;
  color: #fff;
  font-size: 20px;
  font-weight: 600;
  height: 50px;
}

.navbar__item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
}

.account{
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgb(38,90,99);
  background: linear-gradient(180deg, rgba(38,90,99,1) 0%, rgba(0,196,229,1) 100%);
}

.balance{
  padding: 4px 10px;
  border-radius: 20px;
  border: 2px solid #fff;
  font-size: 15px;
  display: flex;
  align-items: center;
  gap: 5px;
  font-weight: 600;
  transition: all 0.3s ease;
}

.balance:hover{
  cursor: pointer;
  background: rgb(245,136,64);
  transition: all 0.3s ease;
}

.balance img{
  margin-left: 5px;
  width: 20px;
  height: 20px;
}

.search{
  border: 2px solid #fff;
  border-radius: 20px;
  padding: 5px 10px;
  display: flex;
  align-items: center;
  gap: 5px;
}

.search input{
  border: none;
  outline: none;
  background-color: transparent;
  color: #fff;
  font-size: 15px;
}

.line__search{
  width: 1px;
  height: 20px;
  background-color: #fff;
}

.choose{
  border-bottom: 2px solid #F58840;
}

.logo{
  width: 40px;
  height: 40px;
}
</style>