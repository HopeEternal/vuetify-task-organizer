<template>
  <div class="team">
    <h1 class="subheading grey--text text--darken-3">Team</h1>

    <v-container class="my-5">
      <v-layout row>
        <v-flex xs12 s6 md4 lg3 v-for="person in team" :key="person.name">
          <v-card text class="text-center ma-3">
            <v-responsive class="pt-4">avatar</v-responsive>
            <v-card-text>
              <div class="subheading">{{person.name}}</div>
              <div class="grey--text">{{person.role}}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn text color="grey">
                <v-icon small left>mdi-message</v-icon>
                <span>Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      team: [
        { name: 'Wilson VolleyBall', role: 'Web Developer' },
        { name: 'Hope Eternal', role: 'Web Developer and Designer' },
        { name: 'Noorullah', role: 'Database Admin' },
        { name: 'Ryan Toyz', role: 'Cyber Security' },
        { name: 'Kira the Scribbluh', role: 'Content Specialist' }
      ]
    };
  }
};
</script>
