<template>
    <div>
        <h2>Contact Us</h2>
        <p>Name: {{ props.name }}</p>
        <p>Phone: {{ props.phone }}</p>
        <p>Owner Name: {{ props.ownername }}</p>
    </div>
    <button :class="[props.isFavourite ? 'btn btn-success' : 'btn btn-danger']">
    {{ props.isFavourite ? 'Favourite' : 'Not Favourite' }}
  </button>
  </template>
  
  <script setup>
import { ref } from 'vue';
import { defineProps } from 'vue';

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
  </script>
  