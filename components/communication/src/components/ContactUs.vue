<template>
    <div>
        <h2>Contact Us</h2>
        <p>Name: {{ name }}</p>
        <p>Phone: {{ phone }}</p>
        <p>Email: {{ email }}</p>
        <p>Owner Name: {{ ownername }}</p>
    </div>
    <div>
        <button :class="[isFavourite? 'btn btn-warning':'btn btn-danger']">{{ isFavourite?'yes':'no' }}</button>
    </div>
  </template>
  
  <script setup>
import { ref } from 'vue';

  const props = defineProps({
    name: String, required: true,
    phone: Number, required: true,
    ownername: String,
    isFavourite: Boolean
  });
  console.log(props);
  
  const email = ref("akhil@gmail.com");
  </script>
  