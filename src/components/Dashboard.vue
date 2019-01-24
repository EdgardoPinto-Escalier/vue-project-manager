<template>
  <div class="dashboard">
    <v-container class="my-3">
      <h2 class="grey--text mb-3">DASHBOARD</h2>
      <v-layout row class="mb-3">
        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('title')" slot="activator">
            <v-icon left small>folder</v-icon>
            <span class="caption">BY PROJECT NAME</span>
          </v-btn>
          <span>Sort by project name</span>
        </v-tooltip>

        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('person')" slot="activator">
            <v-icon left small>person</v-icon>
            <span class="caption">BY PERSON</span>
          </v-btn>
          <span>Sort by person name</span>
        </v-tooltip>

      </v-layout>
      <v-card flat v-for="project in projects" :key="project.title">
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
import db from '@/config/db'

export default {
  data() {
    return {
      projects: []
    }
  },
  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => a[prop] < b[prop] ?  -1 : 1)
    }
  },
  created() {
    db.collection('projects').onSnapshot(res => {
      const changes = res.docChanges();

      changes.forEach(change => {
        if (change.type === 'added') {
          this.projects.push({
            ...change.doc.data(),
            id: change.doc.id
          })
        }
      })
    })
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



