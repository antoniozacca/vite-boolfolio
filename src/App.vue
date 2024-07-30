<script>
import axios from 'axios';
export default {
  name: 'projects',

},
methods:{
  getProject(){
    const result = axios.get('http://127.0.0.1:8000/api/projects')
  }
}
</script>

<template>
  <div id="app"></div>
</template>

<style scoped>






</style>
