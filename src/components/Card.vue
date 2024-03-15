<template>
  <div class="card">
    <a :href="`https://www.themoviedb.org/movie/${aa.id}`">
      <figure>
        <img v-bind:src="`https://media.themoviedb.org/t/p/w300_and_h450_bestv2/${aa.poster_path}`" :alt="aa.title">
        <!-- <img src="https://placehold.it/300x400/ddd/333?text=MoviePoster" alt=""> -->
      </figure>
      <div class="text">
        <h3>{{ aa.title }}</h3>
      </div>
    </a>
  </div>
</template>

<script>
  export default {
    props:['aa'] //옵션 없을때
  }
</script>


<style lang="scss" scoped>
    * { 
    margin: 0;
    padding:0;
    box-sizing: border-box;
    font-family: sans-serif;
    text-decoration: none;
  }

  .card {
    width:20%; padding: 16px;

    @media (max-width:900px){
      width:25%;
    }
    @media (max-width:768px){
      width:33.33%;
    }
    @media (max-width:500px){
      width:50%;
    }
    a {
      display: block;
      border-radius: 16px;
      overflow: hidden;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      figure {
        width:100%;
        height: 0;margin:0;
        padding-bottom: 150%;
        border-radius: 8px;
        overflow: hidden;

        img{
          width: 100%;
          object-fit:cover;
          transition: 0.3s ease-in;
        }
      }
      .text{
        height:80px;
        padding: 16px;
        h3{
          color: #111; 
          transition: 0.3s ease-in;

        }
      }
      &:hover img {
          transform: scale(1.1);
      }
      &:hover h3 {
          color: rgb(96, 158, 167);
      }
    }
  }
</style>