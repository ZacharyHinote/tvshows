<template>
  <div id="app">
    <Header theTitle="Popular TV Shows"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
//import Card from './components/Card.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header//, 
    //Card
  },
data()
{
  return{
    movieList:
    [
      {id: 0, title: "Zero"}
    ]
  }
},
mounted()
{
  axios.get('https://api.themoviedb.org/3/movie/popular?api_key=f905d593315b20381ee61905e48cc7df&language=en-US&page=1')
  .then( (res) => {
    for (i = 0; i < 4; i++) {
      this.movieList.id = i,
      this.movieList.title = res.data.results[i].title
    
    }
  })
}
}

</script>

<style>
* {
  margin: 0;
  padding: 0;
}
</style>
