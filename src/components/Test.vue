<template>
  <div class="title-container">
    <h1 id="maintitle">{{ title }}</h1>
    <router-link to="/" @click="nextAnimation"
      ><img id="logo-mm" src="@/assets/logomm.svg"
    /></router-link>
  </div>
</template>

<script>
export default {
  props: ["title", "nextAnimation"],
  name: "Test",
  data() {
    return {};
  },
};
</script>

<style lang="scss">
.title-container {
  #logo-mm {
    position: absolute;
    bottom: 20px;
    width: 100px;
    left: 50%;
    transform: translateX(-50%);
    z-index: 15;
  }
  h1 {
    position: relative;
    width: 480px;

    margin: 0;

    color: #f1f2f0;
    font-size: 200px;
    line-height: 160px;
    font-family: "Londrina Solid", cursive;
    z-index: 2;

    &::before {
      content: "";
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 100%;
      height: 126px;
      background-color: #382530;
      z-index: -1;
      transition: 0.5s ease-in-out;

      pointer-events: none;
    }

    &:hover {
      &::before {
        transform: translateX(-50%) rotate(-5deg);
      }
    }
  }
  .animate-title {
    pointer-events: none;
    &::before {
      transform: translateX(-50%) scale(20);
    }
  }
}
</style>