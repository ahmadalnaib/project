<script >
export default{
  name:'Home',
  components:{},
  data(){
    return {
      projects:[]
    }

  },

  mounted(){
    fetch('http://localhost:3000/projects')
    .then(response => response.json())
    .then(data => this.projects = data)
    .catch(error => console.log(error))
  }

}

</script>

<template>
  <main>
    <div v-if="projects.length">
      <div v-for="project in projects" :key="project.id">
         <p>{{ project.title }}</p>
      </div>
    </div>

      
  </main>
</template>
