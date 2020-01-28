<template>
  <div class="projects">
    <h1 class="subheading grey--text text--darken-3">Projects</h1>
    <p>hi</p>
    <v-container class="my-5">
      <v-expansion-panels accordion>
        <v-expansion-panel v-for="project in myProjects" :key="project.title">
          <v-expansion-panel-header>{{project.title}}</v-expansion-panel-header>
          <v-expansion-panel-content class="grey--text">
            <div class="font-weight-bold">due by {{project.due}}</div>
            <div>{{project.content}}</div>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Update Portfolio Website",
          person: "Wilson Volleyball",
          due: "March 15th 2019",
          status: "ongoing",
          content:
            "Complete initial drafting and development of porftolio website. This project is contingent on completing current porfolio pieces like Java auto-mailer."
        },
        {
          title: "Get a kick-butt Dev Job",
          person: "Wilson Volleyball",
          due: "April 1st 2020",
          status: "ongoing",
          content:
            "Attend several career fairs and continue networking to begin process of locating the right position."
        },
        {
          title: "Complete CarBidNow Project",
          person: "Hope Eternal",
          due: "June 13th 2020",
          status: "ongoing",
          content:
            "Complete protyping process, copydeck and Mockup. Then begin drafting CarBidNow website using Vue."
        },
        {
          title: "Learn the art of relaxation",
          person: "Hope Eternal",
          due: "Yesterday",
          status: "overdue",
          content: "Chillax. Be like wat-uh. Let the chill flow through you."
        },
        {
          title: "Be an outstanding human",
          person: "Wilson Volleyball",
          due: "Oct 29th 2012",
          status: "complete",
          content:
            "Continue to be an example of greatness for the rest of humanity. From bringing hot tea to his loved ones on a snowy day to helping out his friends in need."
        }
      ]
    };
  },
  computed: {
    myProjects() {
      return this.projects.filter(project => {
        return project.person === "Hope Eternal";
      });
    }
  }
};
</script>
