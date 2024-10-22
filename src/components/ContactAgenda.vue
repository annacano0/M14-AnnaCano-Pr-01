<script setup>
import { reactive } from 'vue'
import ContactForm from './ContactForm.vue'
import ContactList from './ContactList.vue'

let contacts = reactive([])

const manageAddContact = newContact => {
  console.log(newContact.name + ' ' + newContact.telephone)
  contacts.push(newContact)
}
</script>

<template>
  <h1>LLibret de contactes</h1>
  <ContactForm @add-contact="manageAddContact"></ContactForm>

  <ContactList :contacts="contacts"></ContactList>
</template>

<style scoped></style>
