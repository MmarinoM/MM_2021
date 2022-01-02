<template>
  <div class="container-movie">
    <Poplist :top3list="moviesList" />
    <img id="mm-movies" @click="mylog" src="@/assets/mm-movies.svg" />
  </div>
</template>

<script>
import Poplist from "../components/Poplist.vue";
export default {
  components: {
    Poplist,
  },
  data() {
    return {
      moviesList: [
        {
          name: "Dune",
          img: "https://www.journaldugeek.com/content/uploads/2021/09/template-images-jdg-pptx1-1-1.jpg",
        },
        {
          name: "don't look up",
          img: "https://mrmondialisation.org/wp-content/uploads/2021/12/leonardo-dicaprio-in-dont-look-up.jpg",
        },
        {
          name: "Green Knight",
          img: "https://www.premiere.fr/sites/default/files/styles/scale_crop_1280x720/public/2020-02/Capture%20d%E2%80%99e%CC%81cran%202020-02-13%20a%CC%80%2015.38.56.png",
        },
      ],
    };
  },
  methods: {
    mylog() {
      console.log(this.movieList);
    },
  },
};
</script>

<style lang="scss">
#mm-movies {
  width: 350px;
  position: absolute;
  bottom: -50px;
  right: 0;
  z-index: 1;
  transform: rotateY(180deg);
}
</style>