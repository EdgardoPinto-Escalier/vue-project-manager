<template>
  <div class="dashboard">
    <h1 class="grey--text">DASHBOARD</h1>

    <v-container class="my-5">

      <v-layout row class="mb-3">
        <v-btn small flat color="grey">
          <v-icon left small>folder</v-icon>
          <span class="caption text-lowercase">By Project Name</span>
        </v-btn>
        <v-btn small flat color="grey">
          <v-icon left small>person</v-icon>
          <span class="caption text-lowercase">By Person</span>
        </v-btn>
      </v-layout>

      <v-card flat v-for="project in projects" :key="project.person">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">PROJECT TITLE</div>
            <div>{{ project.title }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">PERSON</div>
            <div>{{ project.person }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">DUE ON</div>
            <div>{{ project.due }}</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div class="right">
              <v-chip :class="`${project.status} white--text my-2`">{{ project.status }}</v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
    </v-container>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        { title: 'Angular Site', person: 'Tom Williams', due: '19 Jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Incidunt beatae consequuntur excepturi. Sapiente nisi, omnis doloremque repellat officiis dicta distinctio adipisci eius pariatur eligendi, accusantium dolor repudiandae enim reprehenderit fugiat'},
        { title: 'DevOps Project', person: 'Laura Thomas', due: '31 Dec 2018', status: 'complete', content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Incidunt beatae consequuntur excepturi. Sapiente nisi, omnis doloremque repellat officiis dicta distinctio adipisci eius pariatur eligendi, accusantium dolor repudiandae enim reprehenderit fugiat'},
        { title: 'Vue.js Web Application', person: 'Jhon Curtis', due: '25 Oct 2018', status: 'complete', content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Incidunt beatae consequuntur excepturi. Sapiente nisi, omnis doloremque repellat officiis dicta distinctio adipisci eius pariatur eligendi, accusantium dolor repudiandae enim reprehenderit fugiat'},
        { title: 'Laravel E-Comerce site', person: 'Peter Jackson', due: '12 Jan 2018', status: 'overdue', content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Incidunt beatae consequuntur excepturi. Sapiente nisi, omnis doloremque repellat officiis dicta distinctio adipisci eius pariatur eligendi, accusantium dolor repudiandae enim reprehenderit fugiat'}
      ]
    }
  }
}
</script>

<style>
.project.complete {
  border-left: 5px solid #3cd1c2;
}

.project.ongoing {
  border-left: 5px solid orange;
}

.project.overdue {
  border-left: 5px solid tomato;
}

.v-chip.complete {
  background: #3cd1c2;
}

.v-chip.ongoing {
  background: orange;
}

.v-chip.overdue {
  background: tomato;
}
</style>



