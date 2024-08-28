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

const time = ref(null); 
const texx = ref(""); 


function handleButtonClick() {
  if (time.value) {
    const date = new Date(time.value); 
    const hours = date.getHours(); 
    const minutes = date.getMinutes(); 
    texx.value = `Часы: ${hours}, Минуты: ${minutes}`; 
  } else {
    console.log('Время не выбрано'); 
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
