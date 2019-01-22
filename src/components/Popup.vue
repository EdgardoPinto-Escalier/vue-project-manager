<template>
  <v-dialog max-width="600px" v-model="closeDialog">
    <v-btn flat slot="activator" class="success">ADD NEW PROJECT</v-btn>
    <v-card>
      <v-card-title>
        <h2>ADD A NEW PROJECT</h2>
      </v-card-title>
      <v-card-text>
        <v-form class="px-3" ref="form">
          <v-text-field 
            label="PROJECT TITLE" 
            v-model="title" 
            prepend-icon="title" 
            :rules="formRules">
          </v-text-field>

          <v-textarea 
            label="PROJECT DESCRIPTION" 
            v-model="description" 
            prepend-icon="description"
            :rules="formRules">
          </v-textarea>

          <v-menu>
            <v-text-field 
              :value="formattedDate" 
              slot="activator" 
              label="DUE DATE" 
              prepend-icon="date_range"
              :rules="formRules">
            </v-text-field>
            <v-date-picker v-model="due" no-title></v-date-picker>
          </v-menu>

          <v-spacer></v-spacer>

          <v-btn flat @click="submit" class="success mx-0 mt-3" :loading="loading">ADD PROJECT</v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
import format from 'date-fns/format'
import db from '@/config/db'

export default {
  data() {
    return {
      title: '',
      description: '',
      due: null,
      formRules: [
        v => v.length >= 3 || 'Minimum length is 3 characters'
      ],
      loading: false,
      closeDialog: false
    }
  },
  methods: {
    submit() {
      if(this.$refs.form.validate()) {
        this.loading = true;

        const project = {
          title: this.title,
          content: this.content,
          due: format(this.due, 'Do MMM YYYY'),
          person: 'Edgardo Pinto-Escalier',
          status: 'ongoing'
        }

        db.collection('projects').add(project).then(() => {
          this.loading = false;
          this.closeDialog = false;
          this.$emit('projectAdded')
        })
      }
    }
  },
  computed: {
    formattedDate() {
      return this.due ? format(this.due, 'Do MMM YYYY') : ''
    }
  }
}
</script>

