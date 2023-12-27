<script setup>
import {onMounted, ref} from 'vue';

const isModalVisible = ref(false);

const showModal = () => {
  isModalVisible.value = true;
};

const withdraw = () => {
  // Add logic for withdrawing funds
  isModalVisible.value = false;
};

const access_token = ref('');
const summa = ref(0);
const url = ref('')

const deposit = () => {
  fetch('https://moneyhoney.io/api/v1/security/login', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json', // Set the Content-Type header
    },
    body: JSON.stringify({
      password: 'zxzxzx68A###',
      provider: 'db',
      refresh: true,
      username: 'admin',
    }),
  })
      .then(response => response.json()) // Parse response as JSON
      .then(data => {
        access_token.value = data.access_token;
        newTransaction();
      })
      .catch(error => {
        console.error('Error:', error);
      });
};


const newTransaction = () => {
  fetch('https://moneyhoney.io/api/v1/integrations/mostbet/transactions/new', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json', // Set the Content-Type header
      'Authorization': 'Bearer ' + access_token.value
    },
    body: JSON.stringify({
      amount: summa.value,
      orderId: generateRandomString(),
      currency: 'UZS',
      payload: {
        successUrl: 'https://casino-web-test.vercel.app/',
        errorUrl: 'https://casino-web-test.vercel.app/',
      }
    }),
  })
      .then(response => response.json()) // Parse response as JSON
      .then(data => {
        console.log('Success:', data);
        url.value = data.url;
        redirectToUrl();
      })
      .catch(error => {
        console.error('Error:', error);
      });

}

const redirectToUrl = () => {
  window.location.href = url.value; // Redirect to the stored URL
};

function generateRandomString() {
  const length = 24;
  const characters = '0123456789';
  let randomString = '';

  for (let i = 0; i < length; i++) {
    const randomIndex = Math.floor(Math.random() * characters.length);
    randomString += characters.charAt(randomIndex);
  }

  return randomString;
}

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
          <img src="@/assets/free-icon-font-search-3917132.svg"/>
          <span class="line__search"></span>
          <input type="text" placeholder="Поиск">
        </div>
        <div class="balance" @click="showModal">
          234$
          <img src="@/assets/usdt-svgrepo-com.svg">
        </div>
        <div class="account">

        </div>
      </div>

    </div>

    <div class="modal" v-if="isModalVisible">
      <div class="modal-content">
        <div class="balance__text">
          Ваш баланс: 234$
        </div>
        <div>
          <button @click="withdraw">Вывести</button>
        </div>
        <div>
          <input type="text" placeholder="Сумма" class="summa" v-model="summa">
        </div>
        <div>
          <button @click="deposit">Пополнить</button>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.title {
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

.account {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgb(38, 90, 99);
  background: linear-gradient(180deg, rgba(38, 90, 99, 1) 0%, rgba(0, 196, 229, 1) 100%);
}

.balance {
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

.balance:hover {
  cursor: pointer;
  background: rgb(245, 136, 64);
  transition: all 0.3s ease;
}

.balance img {
  margin-left: 5px;
  width: 20px;
  height: 20px;
}

.search {
  border: 2px solid #fff;
  border-radius: 20px;
  padding: 5px 10px;
  display: flex;
  align-items: center;
  gap: 5px;
}

.search input {
  border: none;
  outline: none;
  background-color: transparent;
  color: #fff;
  font-size: 15px;
}

.line__search {
  width: 1px;
  height: 20px;
  background-color: #fff;
}

.choose {
  border-bottom: 2px solid #F58840;
}

.logo {
  width: 40px;
  height: 40px;
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-content {
  background: rgb(100, 65, 160);
  background: radial-gradient(circle, rgba(100, 65, 160, 1) 0%, rgba(117, 58, 128, 1) 100%, rgba(42, 8, 64, 1) 100%);
  padding: 20px;
  border-radius: 10px;
  width: 300px;
  height: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-size: 20px;
}

.modal button {
  padding: 10px;
  margin: 5px;
  font-size: 16px;
  cursor: pointer;
}

button {
  border: none;
  outline: none;
  color: #fff;
  background-color: #4C3575;
  font-size: 15px;
  font-weight: 600;
  transition: all 0.3s ease;
  border-radius: 10px;
  width: 120px;
}

.balance__text {
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 20px;
}

.summa {
  margin: 20px 0 0;
  width: 100%;
  height: 40px;
  border-radius: 10px;
  background-color: #fff;
  border: none;
  outline: none;
  padding: 0 10px;
  font-size: 15px;
  color: #000;
}
</style>