<template>
    <div class="col-6">
      <div>
        <h2>Contact Us</h2>
        <p>Name: {{ props.name }}</p>
        <p>Phone: {{ props.phone }}</p>
        <p>Owner Name: {{ props.ownername }}</p>
    </div>
    <button @click="toggleFavorite" :class="[props.isFavourite ? 'btn btn-success' : 'btn btn-danger']">
    {{ props.isFavourite ? 'Favourite' : 'Not Favourite' }}
  </button>
    </div>
    <div class="col-6">
      <LuckyNumber :maxNumber="100"/>
    </div>
  </template>
  
  <script setup>
import { ref } from 'vue';
import { defineProps } from 'vue';
import  {defineEmits } from 'vue';
import LuckyNumber from "./LuckyNumber.vue"
const emit = defineEmits(['update-isFavourite']);

const props = defineProps({
  name: {
    type: String,
    required: true
  },
  phone: {
    type: Number,
    required: true
  },
  ownername: {
    type: String
  },
  isFavourite: {
    type: Boolean
  }
});
  console.log(props);
  
  const email = ref("akhil@gmail.com");
  function toggleFavorite() {
    emit('update-isFavourite',props.isFavourite);
  }
  </script>
  