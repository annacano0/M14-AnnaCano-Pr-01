<script setup>
import { ref, computed } from 'vue'

const props = defineProps({
  contacts: Array,
})

let filter = ref('')

const filteredContacts = computed(() => {
  return props.contacts.filter(contact => contact.name.includes(filter.value))
})
</script>

<template>
  <input v-model="filter" type="text" placeholder="Cercar per nom" />
  <ul>
    <li v-for="(contact, index) in filteredContacts" :key="index">
      {{ contact.name }} - <span>{{ contact.telephone }}</span>
    </li>
  </ul>
</template>

<style scoped>
span {
  color: green;
}
</style>
