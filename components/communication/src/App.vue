<template>
  <div id="app">
    <h1>Communication App</h1>
    <input type="text" v-model="myname" placeholder="Enter your name" />
    <div class="row" >
      <div class="col" v-for="contact in contacts" :key="contact.name">
        <ContactUs :name="contact.value" :phone="contact.phone" :ownername="contact.ownername" :isFavourite="contact.isFavourite"
        @update-isFavourite="contact.isFavourite=onUpdatedFromChild($event)" />

      </div>

    </div>
  </div>
</template>

<script setup>
import {  reactive, ref } from "vue";
import ContactUs from "./components/ContactUs.vue"
const myname = ref("Akhil")
const contacts=reactive([
{
  name:"Akhil1",
  phone:9849465498,
  ownername:myname,
  isFavourite:true
},
{
  name:"Akhil2",
  phone:9849465498,
  ownername:myname,
  isFavourite:true
},
{
  name:"Akhil3",
  phone:9849465498,
  ownername:myname,
  isFavourite:false
}
]
)
function onUpdatedFromChild(f){
  return !f;
}
</script>