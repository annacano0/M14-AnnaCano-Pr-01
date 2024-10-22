<script setup>
import { ref, defineEmits } from 'vue'

const emit = defineEmits(['addContact'])
const name = ref('')
const telephone = ref()

const addContact = () => {
  console.log('añadir contacto')
  emit('addContact', { name: name.value, telephone: telephone.value })
  clearForm()
}

const clearForm = () => {
  name.value = ''
  telephone.value = ''
}
</script>

<template>
  <div id="container-contact-form">
    <input v-model="name" type="text" placeholder="Nom del contacte" />
    <input v-model="telephone" type="text" placeholder="Número de telefon" />
    <button @click="addContact">Afegir contacte</button>
  </div>
</template>

<style scoped></style>
