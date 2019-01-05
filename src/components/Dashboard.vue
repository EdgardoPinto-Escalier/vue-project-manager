<template>
  <div class="dashboard">
    <h1 class="grey--text">DASHBOARD</h1>

    <v-container class="my-5">
      <v-card flat class="pa-3">
        <v-layout row wrap>
          <v-flex xs12 md6>
            <div class="caption grey--text">PROJECT TITLE</div>
            <div>New DevOps Project</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">PERSON</div>
            <div>Tom Williams</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">DUE ON</div>
            <div>3rd Apr 2019</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div class="caption grey--text">STATUS</div>
            <div>Ongoing</div>
          </v-flex>
        </v-layout>
      </v-card>
    </v-container>
    
  </div>
</template>

<script>
export default {

}
</script>


