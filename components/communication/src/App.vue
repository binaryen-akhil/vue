<template>
  <div id="app">
    <h1>Communication App</h1>
    <ContactUs name="Akhil" phone="9849465498" :ownername="myname"/>
  </div>
</template>

<script setup>
import ContactUs from "./components/ContactUs.vue"
const myname = "Akhil"
</script>