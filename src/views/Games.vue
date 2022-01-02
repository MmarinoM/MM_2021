<template>
  <div class="games-container">
    <poplist :top3list="gamesList" />
    <img id="mm-games" src="@/assets/mm-games.svg" />
  </div>
</template>

<script>
import Poplist from "../components/Poplist.vue";
export default {
  components: { Poplist },
  data() {
    return {
      gamesList: [
        {
          name: "it takes two",
          img: "https://infinity-area.com/statics/infinitycms/redact/It%20Takes%20Cover.jpg",
        },
        {
          name: "Ff VII remake",
          img: "https://img.phonandroid.com/2021/12/FF7.jpg",
        },
        {
          name: "Valheim",
          img: "https://image.jeuxvideo.com/medias-crop-1200-675/161297/1612967164-2539-card.jpg",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
#mm-games {
  width: 350px;
  position: absolute;
  bottom: -50px;
  right: 0;
  z-index: 1;
  transform: rotateY(180deg);
}
</style>