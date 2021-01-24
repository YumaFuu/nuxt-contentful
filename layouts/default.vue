<template>
  <v-app>
    <v-app-bar
      app
      >
      <v-tabs
        fixed-tabs
        color="pink darken-1"
        >
        <v-tab nuxt to="/">Home</v-tab>
        <v-tab nuxt to="/garally">Garally</v-tab>
        <v-tab nuxt to="/profile">Profile</v-tab>
      </v-tabs>
    </v-app-bar>
    <v-main>
      <v-container>
        <div>
          <nuxt />
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>
