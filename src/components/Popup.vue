<template>
  <v-dialog max-width="600px">
    <v-btn flat slot="activator" class="success">ADD NEW PROJECT</v-btn>
    <v-card>
      <v-card-title>
        <h2>ADD A NEW PROJECT</h2>
      </v-card-title>
      <v-card-text>
        <v-form class="px-3">
          <v-text-field label="PROJECT TITLE" v-model="title" prepend-icon="title"></v-text-field>
          <v-textarea label="PROJECT DESCRIPTION" v-model="description" prepend-icon="description"></v-textarea>
          <v-btn flat class="success mx-0 mt-3">ADD PROJECT</v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      description: ''
    }
  }
}
</script>

