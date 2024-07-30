<script>
import axios from 'axios';
export default {
  name: 'projects',
  data() {
  return {
  projects: []
  }
},
  created() {
    this.getProject();
  },
  methods: {
    getProject() {
      const result= axios.get('http://127.0.0.1:8000/api/projects')
        .then((data) => {
          this.projects = data.data.resource;
          console.log(projects);
        });
    }
  }
};
</script>

<template>
  <div id="app">

    <div class="container mt-4">
      <h1 class="mb-4">Projects</h1>
      <div class="row">
        <div class="col-md-4 mb-4" v-for="project in projects" :key="project.id">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">{{ project.title }}</h5>
              <p class="card-text">{{ project.content }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  border-radius: 0.25rem;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card-title {
  font-size: 1.25rem;
  font-weight: 500;
}

.card-text {
  font-size: 1rem;
}
</style>