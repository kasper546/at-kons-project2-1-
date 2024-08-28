<template>
  <p class="hours_minites">{{ texx }}</p>
  <Calendar id="calendar-timeonly" v-model="time" timeOnly />
  <Button icon="pi pi-calendar" @click="handleButtonClick"/>
</template>

<script setup>
import Calendar from 'primevue/calendar';
import Button from 'primevue/button';
import 'primeicons/primeicons.css'; 
import { ref } from 'vue';

const time = ref(null); // Время, выбранное пользователем
const texx = ref(""); 

// Обработчик клика на кнопку
function handleButtonClick() {
  if (time.value) {
    const date = new Date(time.value); // Создаем новый объект Date
    const hours = date.getHours(); // Получаем часы
    const minutes = date.getMinutes(); // Получаем минуты
    texx.value = `Часы: ${hours}, Минуты: ${minutes}`; // Выводим часы и минуты в консоль
  } else {
    console.log('Время не выбрано'); // Выводим, если время не выбрано
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
