<script setup>
defineProps({
  registration: Object
})
</script>

<template>
  <div v-if="registration">
    <h2>Event Registration</h2>

    <p>Participant Name: {{ registration.participantName }}</p>
    <p>Student ID: {{ registration.studentId }}</p>
    <p>Event: {{ registration.event }}</p>
    <p>Attendance Type: {{ registration.attendance }}</p>
    <p>Email: {{ registration.email }}</p>
  </div>
</template>