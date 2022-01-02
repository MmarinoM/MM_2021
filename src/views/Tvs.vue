<template>
  <div class="tvs-container">
    <Poplist :top3list="tvsList" />
    <img id="mm-tvs" src="@/assets/mm-tvs.svg" />
  </div>
</template>

<script>
import Poplist from "../components/Poplist.vue";
export default {
  components: { Poplist },
  data() {
    return {
      tvsList: [
        {
          name: "Arcane",
          img: "https://www.ecranlarge.com/media/cache/1600x1200/uploads/articles/001/409/182/arcane-photo-1409181-large.jpg",
        },
        {
          name: "handmaid's tale",
          img: "https://artsy-media-uploads.s3.amazonaws.com/v4gsD7Y0YDfSbVgP--e-_g%2Fcustom-Custom_Size___GettyImages-1125162215+copy.jpg",
        },
        {
          name: "Invincible",
          img: "https://www.programme-tv.net/imgre/fit/https.3A.2F.2Fi.2Epmdstatic.2Enet.2Ftel.2F2021.2F03.2F17.2F714e5ee8-eedf-4e42-bd03-106072c3b647.2Epng/1200x600/crop-from/top/credit/1/quality/80/invincible-prime-video-de-quel-comics-la-serie-est-elle-adaptee.jpg",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
#mm-tvs {
  width: 350px;
  position: absolute;
  bottom: -50px;
  right: 0;
  z-index: 1;
}
</style>