<template>
    <div>
        <div v-for="movie in movieList" v-bind:key="movie.id" class = "movie">
            <h1>{{movie.title}}</h1>
        </div>
    </div>
</template>

<script> 
export default {
    name: "Movies",
    props: ['movieList']
}

</script> 

<style scoped>
.movie {
    background-color: white;
}

</style>