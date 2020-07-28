

<template>
  <div>
      <h1>Star Wars!</h1>
      {{starwars[0].name}}
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
    fetch(`https://swapi.dev/api/people/10`)
    .then(r => r.json() ) 
    .then(response => this.starwars = response)
    }
  },
  created(){
    this.getData();
  }

}
</script>