<template>
  <div>
    <h1>Star Wars!</h1>

   <div v-for="planet in starwars.results" :key="planet.name">
    {{planet.name}}
   </div>
  
  </div>
</template>


<script>
export default {
  name: 'StarWars',
data(){
  return {
    starwars: []
    }
  },
  methods: {
    getData(){
    fetch(`https://swapi.dev/api/planets`)
    .then(r => r.json() ) 
    .then(response => this.starwars = response)
    }
  },
  created(){
    this.getData();
  }

}
</script>