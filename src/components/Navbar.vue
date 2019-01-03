<template>
  <nav>
    <v-toolbar flat app>
      <v-toolbar-side-icon class="grey--text" @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">PROJECT</span>
        <span>MANAGER</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn flat color="grey">
        <span>SIGN OUT</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
    </v-toolbar>

    <v-navigation-drawer app v-model="drawer" class="indigo">
      <p>TEST</p>
    </v-navigation-drawer>
  </nav>
</template>


<script>
export default {
  data() {
    return {
      drawer: false
    }
  }
}
</script>
