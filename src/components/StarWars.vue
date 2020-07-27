

<template>
  <div>
      <h1>Star Wars!</h1>
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
    fetch('starwars.json')
    .then(r => r.json())
    .then(response => this.starwars = response.data.results)
    }
  },
  created(){
    this.getData();
  }

}
</script>