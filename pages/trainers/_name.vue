<template>
  <div>
    <v-container>
      <v-breadcrumbs :items="items" class="pl-0"></v-breadcrumbs>
      <div class="title">{{ name }}</div>
      <v-divider></v-divider>
      <v-row class="mt-3" wrap>
        <v-col cols="12" sm="5">
          <div class="subtitle-1">Tags</div>
          <v-divider class="my-2"></v-divider>
          <v-chip color="primary" x-small outlined>Strength</v-chip>
          <v-chip color="primary" x-small outlined>Cardio</v-chip>
          <v-chip color="primary" x-small outlined>Weight Management</v-chip>
          <v-card class="mt-2">
            <v-card-title>360</v-card-title>
            <v-card-text>Hours Logged</v-card-text>
          </v-card>
          <v-card class="mt-2">
            <v-card-text>
              <div class="subtitle-1">Default Availability</div>
              <v-simple-table dense>
                <thead>
                  <th>M</th>
                  <th>T</th>
                  <th>W</th>
                  <th>T</th>
                  <th>F</th>
                  <th>S</th>
                  <th>S</th>
                </thead>
                <tbody>
                  <td colspan="7">Not Set</td>
                </tbody>
              </v-simple-table>
            </v-card-text>
            <v-card-actions>
              <v-btn small>Set Availability</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
        <v-col cols="12" sm="7">
          <div class="subtitle-1">Appointments</div>
          <v-divider class="my-2"></v-divider>
          <v-btn-toggle v-model="viewType" color="primary">
            <v-btn text value="list" small>
              List View
            </v-btn>
            <v-btn text value="calendar" small>
              Calendar View
            </v-btn>
          </v-btn-toggle>
          <v-card class="mt-2 px-2 pt-2" flat>
            <span class="font-weight-bold pr-5">Monday</span>
            <span>May 8</span>
            <v-row>
              <v-col cols="12" md="3">
                <span class="font-weight-bold">09:30 - 10:30</span>
              </v-col>
              <v-col cols="12" md="6">
                Some Title Appointment
              </v-col>
              <v-col cols="12" md="6"
                >Attendee 1, Attendee 2, Attendee 3...</v-col
              >
              <v-col cols="12" md="6" class="appointment-buttons">
                <v-btn small>Details</v-btn>
                <v-btn small>Delete</v-btn>
              </v-col>
            </v-row>
          </v-card>
          <v-divider></v-divider>
          <v-card class="px-2 pt-2" flat>
            <span class="font-weight-bold pr-5">Tuesday</span>
            <span>May 9</span>
            <v-row>
              <v-col cols="12" md="3">
                <span class="font-weight-bold">09:30 - 10:30</span>
              </v-col>
              <v-col cols="12" md="6">
                Some Other Appointment
              </v-col>
              <v-col cols="12" md="6">Attendee 1</v-col>
              <v-col cols="12" md="6" class="appointment-buttons">
                <v-btn small>Details</v-btn>
                <v-btn small>Delete</v-btn>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12" md="3">
                <span class="font-weight-bold">10:30 - 10:30</span>
              </v-col>
              <v-col cols="12" md="6">
                Second Appointment
              </v-col>
              <v-col cols="12" md="6">Attendee 5</v-col>
              <v-col cols="12" md="6" class="appointment-buttons">
                <v-btn small>Details</v-btn>
                <v-btn small>Delete</v-btn>
              </v-col>
            </v-row>
          </v-card>
          <v-divider></v-divider>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      viewType: 'list',
      name: this.$route.params.name,
      items: [
        {
          text: 'Trainers',
          to: '/trainers',
          exact: true
        },
        {
          text: this.$route.params.name
        }
      ]
    }
  }
}
</script>

<style scoped>
@media (min-width: 768px) {
  .appointment-buttons {
    text-align: right;
  }
}
</style>
