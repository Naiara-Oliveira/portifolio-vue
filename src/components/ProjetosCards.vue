<template>
    <v-card class="project-card">
      <v-img :src="project.image" height="200"></v-img>
      <v-card-title>{{ project.title }}</v-card-title>
      <v-card-subtitle>{{ project.subtitle }}</v-card-subtitle>
      <v-card-text>{{ project.description }}</v-card-text>
      <v-card-actions>
        <v-btn color="primary" :href="project.url" target="_blank">Ver projeto</v-btn>
      </v-card-actions>
    </v-card>
    
  </template>
  
  <script>
  export default {
    name: 'ProjetosCards',
    props: {
      project: {
        type: Object,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  .project-card {
    max-width: 500px;
    margin: 20px;
  }
  </style>
  