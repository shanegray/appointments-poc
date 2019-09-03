<template>
  <nav>
    <v-app-bar app flat>
      <v-container>
        <v-layout row>
          <v-toolbar-title class="text-uppercase grey--text">
            <span class="font-weight-light">Appointments</span>
            <span>POC</span>
          </v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn text color="grey">
            <span>Sign Out</span>
            <v-icon right>mdi-exit-to-app</v-icon>
          </v-btn>
        </v-layout>
      </v-container>
      <template v-slot:extension>
        <v-tabs centered fixed-tabs background-color="transparent">
          <v-tab to="/">Home</v-tab>
          <v-tab to="/trainers">Trainers</v-tab>
          <v-tab to="/settings">Settings</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>
  </nav>
</template>
