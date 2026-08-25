
<template>
  <div class="form-container">
    <h2>Event Registration</h2>

    <form @submit.prevent="submitForm">
      <div class="form-group">
        <label for="participantName">Participant Name</label>
        <input
          id="participantName"
          type="text"
          v-model="participantName"
          required
        />
      </div>

      <div class="form-group">
        <label for="studentId">Student ID</label>
        <input
          id="studentId"
          type="text"
          v-model="studentId"
          required
        />
      </div>

      <div class="form-group">
        <label for="event">Event</label>
        <select id="event" v-model="event" required>
          <option value="" disabled>Select an event</option>
          <option value="IT Week">IT Week</option>
          <option value="Technology Summit">Technology Summit</option>
          <option value="Student Leadership Seminar">
            Student Leadership Seminar
          </option>
        </select>
      </div>

      <div class="form-group">
        <label>Attendance Type</label>

        <div class="radio-group">
          <label>
            <input
              type="radio"
              value="On-site"
              v-model="attendanceType"
            />
            On-site
          </label>

          <label>
            <input
              type="radio"
              value="Online"
              v-model="attendanceType"
            />
            Online
          </label>
        </div>
      </div>

      <div class="form-group">
        <label for="email">Email</label>
        <input
          id="email"
          type="email"
          v-model="email"
          required
        />
      </div>

      <button type="submit">
        Register for Event
      </button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'


const participantName = ref('')
const studentId = ref('')
const event = ref('')
const attendanceType = ref('')
const email = ref('')

const emit = defineEmits(['event-submitted'])

// Submit form
const submitForm = () => {
  const registrationInfo = {
    participantName: participantName.value,
    studentId: studentId.value,
    event: event.value,
    attendanceType: attendanceType.value,
    email: email.value
  }

  // Send registration object to parent
  emit('event-submitted', registrationInfo)
}
</script>
