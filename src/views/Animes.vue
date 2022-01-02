<template>
  <div class="animes-container">
    <poplist :top3list="animesList" />
    <img id="mm-animes" src="@/assets/mm-animes.svg" />
  </div>
</template>

<script>
import Poplist from "../components/Poplist.vue";
export default {
  components: { Poplist },
  data() {
    return {
      animesList: [
        {
          name: "Star Wars visions",
          img: "https://sm.ign.com/ign_fr/screenshot/default/blob_nqa5.jpg",
        },
        {
          name: "Ranking of kings",
          img: "https://media.senscritique.com/media/000020285445/1200/Ranking_of_Kings.jpg",
        },
        {
          name: "Demon slayer",
          img: "https://i.jeuxactus.com/datas/jeux/d/e/demon-slayer/xl/demon-slayer-601d9034175be.jpg",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
#mm-animes {
  width: 350px;
  position: absolute;
  bottom: -50px;
  right: 0;
  z-index: 1;
  transform: rotateY(180deg);
}
</style>