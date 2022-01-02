<template>
  <div class="albums-container">
    <img id="mm-albums" src="@/assets/mm-albums.svg" />
    <poplist :top3list="albumsList" />
  </div>
</template>

<script>
import Poplist from "../components/Poplist.vue";
export default {
  components: { Poplist },
  data() {
    return {
      albumsList: [
        {
          name: "l'étrange histoire de mr anderson",
          img: "https://cloudfront-eu-central-1.images.arcpublishing.com/leparisien/NJPJ24JZX5D3HJSJLO3QK7GGJQ.jpg",
        },
        {
          name: "Donda",
          img: "https://www.nme.com/wp-content/uploads/2021/07/Donda-Kanye-West-livestream-two.jpg",
        },
        {
          name: "QALF INFINITY",
          img: "https://yard.media/wp-content/uploads/2018/08/damso-litophedion-genie-yard-guillaume-durand-2.jpg",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
#mm-albums {
  width: 350px;
  position: absolute;
  bottom: -50px;
  right: 0;
  z-index: 1;
}
.albums-container {
  li {
    h2 {
      font-size: 60px !important;
    }
  }
}
</style>