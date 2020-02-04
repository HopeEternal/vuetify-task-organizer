<template>
  <div class="text-center">
    <v-dialog v-model="dialog" width="500">
      <template v-slot:activator="{ on }">
        <v-btn class="success" dark v-on="on">Add New Project</v-btn>
      </template>
      <v-card>
        <v-card-title class="headline grey lighten-2" primary-title
          >Add a New Project</v-card-title
        >
        <v-card-text>
          <v-form class="px-3" ref="form">
            <v-text-field
              label="Title"
              v-model="title"
              prepend-icon="mdi-folder"
              :rules="inputRules"
            ></v-text-field>
            <v-textarea
              label="Information"
              v-model="content"
              prepend-icon="mdi-pencil"
              :rules="inputRules"
            ></v-textarea>

            <v-menu max-width="290">
              <template v-slot:activator="{ on }">
                <v-text-field
                  :value="formattedDate"
                  label="Due date"
                  prepend-icon="mdi-calendar-range"
                  v-on="on"
                  :rules="inputRules"
                ></v-text-field>
              </template>
              <v-date-picker v-model="due"></v-date-picker>
            </v-menu>

            <v-btn text class="success mx-0 mt-3" @click="submit"
              >Add Project</v-btn
            >
          </v-form>
        </v-card-text>
      </v-card>
    </v-dialog>
  </div>
</template>
<script>
import format from 'date-fns/format';
import db from '@/fb';
export default {
  data() {
    return {
      title: '',
      content: '',
      due: null,
      inputRules: [v => v.length >= 3 || 'Minimum length is 3 characters']
    };
  },
  methods: {
    submit() {
      if (this.$refs.form.validate()) {
        //Submit Form
        const project = {
          title: this.title,
          content: this.content,
          due: format(parseInt(this.due), 'Do MMM yyyy'),
          person: 'Hope Eternal',
          status: 'ongoing'
        };
        db.collection('projects')
          .add(project)
          .then(() => {
            console.log('Added to db.');
          });
      }
    }
  },
  computed: {
    formattedDate() {
      return this.due ? format(parseInt(this.due), 'do MMM yyyy') : '';
    }
  }
};
</script>
