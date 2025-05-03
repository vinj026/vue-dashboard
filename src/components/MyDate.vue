<template>
  <div id="containerDate">
    <h1>{{ day }}</h1>
    <p>{{ date }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const day = ref("");
const date = ref("");

const d = new Date();
const dayNames = [
  "Sunday",
  "Monday",
  "Tuesday",
  "Wednesday",
  "Thursday",
  "Friday",
  "Saturday",
];
day.value = dayNames[d.getDay()];

const rawDate = d.getDate(); // Tanggal (1–31)
const year = d.getFullYear();
const months = [
  "January",
  "February",
  "March",
  "April",
  "May",
  "June",
  "July",
  "August",
  "September",
  "October",
  "November",
  "December",
];
let month = months[d.getMonth()];

date.value = `${rawDate} ${month} ${year}`;
</script>

<style scoped>
#containerDate {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: start;
}

p,
h1 {
  margin: 0;
  padding: 0;
}
</style>
