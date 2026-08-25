<script setup>
import { ref } from 'vue'
import EventForm from './components/Eventform.vue'
import EventDisplay from './components/EventDisplay.vue'

const registration = ref(null)

const handleEventSubmitted = (data) => {
  registration.value = data
}
</script>

<template>
  <main class="app">
    <h1>College Event Registration</h1>

    <div class="container">
      <EventForm @event-submitted="handleEventSubmitted" />

      <EventDisplay :registration="registration" />
    </div>
  </main>
</template>
