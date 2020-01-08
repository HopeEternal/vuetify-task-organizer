<template>
  <div class="dashboard">
    <h1 class="subheading grey--text text--darken-3">Dashboard</h1>

    <v-container class="my-5">
      <v-card flat class="pa-3" v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project Title</div>
            <div>{{project.title}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{project.person}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due By</div>
            <div>{{project.due}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Status</div>
            <div>{{project.status}}</div>
          </v-flex>
        </v-layout>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: 'Update Portfolio Website',
          person: 'Wilson Volleyball',
          due: 'March 15th 2019',
          status: 'ongoing',
          content:
            'Complete initial drafting and development of porftolio website. This project is contingent on completing current porfolio pieces like Java auto-mailer.'
        },
        {
          title: 'Get a kick-butt Dev Job',
          person: 'Wilson Volleyball',
          due: 'April 1st 2020',
          status: 'ongoing',
          content:
            'Attend several career fairs and continue networking to begin process of locating the right position.'
        },
        {
          title: 'Complete CarBidNow Project',
          person: 'Hope Eternal',
          due: 'June 13th 2020',
          status: 'ongoing',
          content:
            'Complete protyping process, copydeck and Mockup. Then begin drafting CarBidNow website using Vue.'
        },
        {
          title: 'Learn the art of relaxation',
          person: 'Hope Eternal',
          due: 'Yesterday',
          status: 'overdue',
          content: 'Chillax. Be like wat-uh. Let the chill flow through you.'
        },
        {
          title: 'Be an outstanding human',
          person: 'Wilson Volleyball',
          due: 'Oct 29th 2012',
          status: 'complete',
          content:
            'Continue to be an example of greatness for the rest of humanity. From bringing hot tea to his loved ones on a snowy day to helping out his friends in need.'
        }
      ]
    };
  }
};
</script>

<style>
.project.complete {
  border-left: 4px solid #3cd1c2;
}
.project.ongoing {
  border-left: 4px solid orange;
}
.project.overdue {
  border-left: 4px solid tomato;
}
</style>