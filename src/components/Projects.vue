<template>
  <div class="projects">
    

    <v-container class="my-3">
      <h2 class="grey--text mb-3">PROJECTS</h2>
      <v-expansion-panel>
        <v-expansion-panel-content v-for="project in myProjects" :key="project.title">
          <div slot="header">{{ project.title }}</div>
          <v-card>
            <v-card-text class="px-4 grey--text">
              <div class="font-weight-bold">Due on: {{ project.due }}</div>
              <div>{{ project.content }}</div>
            </v-card-text>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>
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
  },
  computed: {
    myProjects() {
      return this.projects.filter(project => {
        return project.person === 'Tom Williams'
      })
    }
  }
}
</script>
