<template>
  <v-container>
    <v-row dense justify="start" align="baseline">
      <v-col cols="auto mr-5">
        <div class="title">Trainers</div>
      </v-col>
      <v-col cols="auto" md="6">
        <v-text-field
          solo
          label="Search Trainers"
          prepend-inner-icon="mdi-magnify"
        ></v-text-field>
      </v-col>
    </v-row>
    <v-divider></v-divider>
    <v-container>
      <v-card v-for="trainer in trainers" :key="trainer.name" flat>
        <v-layout row wrap class="px-5 py-3">
          <v-flex xs12 sm4 md3>
            <div class="caption grey--text">Trainer</div>
            <div class="subtitle-1">
              <nuxt-link :to="`/trainers/${trainer.name}`">{{
                trainer.name
              }}</nuxt-link>
            </div>
          </v-flex>
          <v-flex xs12 sm8 md4 class="pr-5">
            <div class="caption grey--text">Days Booked</div>
            <v-simple-table dense>
              <thead>
                <tr>
                  <th v-for="(booking, i) in trainer.bookings" :key="i">
                    {{ booking.d }}
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td v-for="(booking, i) in trainer.bookings" :key="i">
                    <div :class="`day-box green lighten-${booking.v}`"></div>
                  </td>
                </tr>
              </tbody>
            </v-simple-table>
          </v-flex>
          <v-flex xs12 md4>
            <div class="caption grey--text mb-5">Capacity</div>
            <v-progress-linear
              :value="trainer.hours"
              height="20"
            ></v-progress-linear>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
    </v-container>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      trainers: [
        {
          name: 'Trainer 1',
          bookings: [
            { d: 'M', v: 1 },
            { d: 'T', v: 2 },
            { d: 'W', v: 3 },
            { d: 'T', v: 4 },
            { d: 'F', v: 2 },
            { d: 'S', v: 1 },
            { d: 'S', v: 1 }
          ],
          hours: 50
        },
        {
          name: 'Trainer 1',
          bookings: [
            { d: 'M', v: 1 },
            { d: 'T', v: 2 },
            { d: 'W', v: 3 },
            { d: 'T', v: 4 },
            { d: 'F', v: 2 },
            { d: 'S', v: 1 },
            { d: 'S', v: 1 }
          ],
          hours: 60
        },
        {
          name: 'Trainer 1',
          bookings: [
            { d: 'M', v: 1 },
            { d: 'T', v: 2 },
            { d: 'W', v: 3 },
            { d: 'T', v: 4 },
            { d: 'F', v: 2 },
            { d: 'S', v: 1 },
            { d: 'S', v: 1 }
          ],
          hours: 20
        },
        {
          name: 'Trainer 1',
          bookings: [
            { d: 'M', v: 1 },
            { d: 'T', v: 2 },
            { d: 'W', v: 3 },
            { d: 'T', v: 4 },
            { d: 'F', v: 2 },
            { d: 'S', v: 1 },
            { d: 'S', v: 1 }
          ],
          hours: 40
        },
        {
          name: 'Trainer 1',
          bookings: [
            { d: 'M', v: 1 },
            { d: 'T', v: 2 },
            { d: 'W', v: 3 },
            { d: 'T', v: 4 },
            { d: 'F', v: 2 },
            { d: 'S', v: 1 },
            { d: 'S', v: 1 }
          ],
          hours: 5
        }
      ]
    }
  }
}
</script>

<style>
.day-box {
  width: 10px;
  height: 10px;
}
</style>
