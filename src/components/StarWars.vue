<template>
  <div>
  <h1>Star Wars!</h1>
  <div v-for="(planet) in starwars.results" :key="planet.name">
  <h5>Name</h5>
    {{planet.name}}
  <h5>Full Rotation</h5>
    {{planet.rotation_period}}
  <h5>Days in Year</h5>
    {{planet.orbital_period}}
  <h5>Climate</h5>
    {{planet.climate}}
  <h5>Terrain</h5>
    {{planet.terrain}}
   <h5>Population</h5>
    {{planet.population}}
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