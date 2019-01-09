<template>
  <div class="team">
    <h1 class="grey--text">TEAM</h1>

    <v-container class="my-5">
      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
          <v-card flat class="text-xs-center ma-3">
            <v-responsive class="pt-4">
              image goes here
            </v-responsive>
            <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn flat color="grey">
                <v-icon small left>message</v-icon>
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
        { name: 'Edgardo Pinto-Escalier', role: 'Web Developer/DevOps' },
        { name: 'Tom Williams', role: 'UX/UI Designer' },
        { name: 'Laura Thomas', role: 'Senior Back-End Developer' },
        { name: 'Paul Jones', role: 'SEO Specialist' },
        { name: 'Ann Wilson', role: 'Sales Manager' }
      ]
    }
  }
}
</script>