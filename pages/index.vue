<template>
  <div>
    <v-container grid-list-md>
      <v-layout row wrap justify-space-around>
        <v-flex>
          <v-card class="dash-card">
            <v-card-title>7</v-card-title>
            <v-card-text>Appointments Today</v-card-text>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card class="dash-card">
            <v-card-title>2</v-card-title>
            <v-card-text>Trainers Booked</v-card-text>
          </v-card>
        </v-flex>
        <v-flex>
          <v-card class="dash-card">
            <v-card-title>21</v-card-title>
            <v-card-text>Appointments This Week</v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
    <v-container>
      <div class="title mb-2">Today's Appointments</div>
      <v-divider></v-divider>
    </v-container>
    <v-container>
      <v-card v-for="(appointment, i) in appointments" :key="i" flat>
        <v-layout row wrap class="px-5 py-3">
          <v-flex xs12>
            <div class="subtitle-1">{{ appointment.time }}</div>
          </v-flex>
          <v-flex xs6 md3>
            <div class="caption grey--text">Trainer</div>
            <div>{{ appointment.trainer }}</div>
          </v-flex>
          <v-flex xs6 md3>
            <div class="caption grey--text">Appointment Title</div>
            <div>{{ appointment.title }}</div>
          </v-flex>
          <v-flex xs6 md4>
            <div class="caption grey--text">Attendees</div>
            <div>{{ appointment.attendees }}.</div>
          </v-flex>
          <v-flex xs12 md2>
            <div class="right pt-2">
              <v-btn small>View Details</v-btn>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
    </v-container>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      appointments: [
        {
          time: '09:30 - 10:30',
          trainer: 'Trainer 1',
          title: 'Title of Appointment',
          attendees: 'Person 1, Person 2, Person ..'
        },
        {
          time: '09:30 - 10:30',
          trainer: 'Trainer 2',
          title: 'AN Other Title',
          attendees: 'Person 1'
        },
        {
          time: '10:30 - 11:30',
          trainer: 'Trainer 1',
          title: 'Title of Appointment',
          attendees: 'Person 1, Person 2, Person ..'
        },
        {
          time: '10:30 - 12:30',
          trainer: 'Trainer 1',
          title: 'Title of Appointment',
          attendees: 'Person 1, Person 2, Person ..'
        },
        {
          time: '12:30 - 13:00',
          trainer: 'Trainer 1',
          title: 'Title of Appointment',
          attendees: 'Person 1, Person 2, Person ..'
        }
      ]
    }
  }
}
</script>
<style scoped>
.dash-card {
  min-width: 150px;
}
</style>
