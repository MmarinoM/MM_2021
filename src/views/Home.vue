<template>
  <div class="home">
    <div class="bubble-container">
      <div class="bubble-text">
        <h2>MY TOP 3 OF THE YEAR</h2>
        <img id="elipse-purple" src="@/assets/elipse-purple.svg" />
      </div>
      <div class="bubble-mm">
        <img id="mm-home" src="@/assets/mm-home.svg" />
        <img class="elipse" src="@/assets/elipse1.svg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
};
</script>
<style lang="scss">
.bubble-container {
  padding-top: 70px;
  display: flex;
  justify-content: center;
  align-items: flex-end;
}
.bubble-text {
  position: relative;
  min-height: 550px;
  z-index: 1;
  h2 {
    font-size: 100px;
    max-width: 350px;
    color: #f1f2f0;
    font-family: "Londrina Solid", cursive;
    z-index: 5;
    margin-bottom: 0;
    text-align: right;
    margin-top: 20px;

    padding-right: 20px;
  }
  #elipse-purple {
    width: 400px;
    position: absolute;
    top: 0;
    right: -100px;
    z-index: -1;
    animation: circlemove 12s linear infinite;
  }
}
.bubble-mm {
  display: flex;
  justify-content: center;
  align-items: center;

  position: relative;
  #mm-home {
    width: 500px;
    position: absolute;
    right: -100px;
    z-index: 1;
  }
  .elipse {
    animation: circlemoveAlt 12s linear infinite;
  }
}

@keyframes circlemove {
  0% {
    transform: translate(-0px, 0px) rotate(0.02deg);
  }
  25% {
    transform: translate(-10px, 10px) rotate(0.02deg);
  }
  50% {
    transform: translate(-0px, 10px) rotate(0.02deg);
  }
  75% {
    transform: translate(-10px, 0px) rotate(0.02deg);
  }
  100% {
    transform: translate(-0px, 0px) rotate(0.02deg);
  }
}
@keyframes circlemoveAlt {
  0% {
    transform: translate(-0px, 0px) rotate(0.02deg);
  }
  25% {
    transform: translate(10px, -10px) rotate(0.02deg);
  }
  50% {
    transform: translate(-0px, -10px) rotate(0.02deg);
  }
  75% {
    transform: translate(10px, 0px) rotate(0.02deg);
  }
  100% {
    transform: translate(-0px, 0px) rotate(0.02deg);
  }
}
@keyframes circlemove--small {
  0% {
    transform: translate(-0px, 0px) rotate(0.02deg);
  }
  25% {
    transform: translate(6px, 6px) rotate(0.02deg);
  }
  50% {
    transform: translate(-0px, 6px) rotate(0.02deg);
  }
  75% {
    transform: translate(6px, 0px) rotate(0.02deg);
  }
  100% {
    transform: translate(-0px, 0px) rotate(0.02deg);
  }
}
</style>
