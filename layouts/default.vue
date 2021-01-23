<template>
  <v-app>
    <v-app-bar
      app
      absolute
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

<style>
.v-application{
  font-family: 'M PLUS Rounded 1c', sans-serif;
}
</style>

