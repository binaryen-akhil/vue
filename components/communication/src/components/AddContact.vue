<template>
    <div class="contianer">
        <h2>Add Contact</h2>
        <form @submit.prevent="addContact">
            <div class="mb-3">
                <label for="name" class="form-label">Name</label>
                <input type="text" class="form-control" id="name" v-model="newContact.name" required>
            </div>
            <div class="mb-3">
                <label for="phone" class="form-label">Phone</label>
                <input type="text" class="form-control" id="phone" v-model="newContact.phone" required>
            </div>
            <div class="mb-3">
                <label for="ownerName" class="form-label">Owner Name</label>
                <input type="text" class="form-control" id="ownerName" v-model="newContact.ownerName" required> 
            </div>
            <button type="submit" class="btn btn-primary">Add Contact</button>
        </form>
    </div>
</template>
<script setup>
import { reactive } from 'vue';
 const newContact = reactive({
    name: '',
    phone: '',
    ownerName:''
    });
const emit = defineEmits(['add-contact']);
function addContact() {
    // Emit the new contact data to the parent component
    emit('add-contact', { ...newContact });
    
    // Clear the form fields
    newContact.name = '';
    newContact.phone = '';
    newContact.ownerName = '';
    
}

</script>