<template>
  <div class="container">
    <div class="center">
      <div class="header">
        <Test title="2021" :nextAnimation="next" />
        <div id="nav">
          <router-link to="/movies" @click="next">MOVIES</router-link>
          <router-link to="/tvs" @click="next">TV SERIES</router-link>
          <router-link to="/games" @click="next">VIDEO GAMES</router-link>
          <router-link to="/animes" @click="next">ANIMES</router-link>
          <router-link to="/albums" @click="next">ALBUMS</router-link>
        </div>
      </div>
      <router-view />
    </div>
  </div>
</template>

<script>
import Test from "./components/Test.vue";
export default {
  components: {
    Test,
  },
  data() {
    return {
      colors: [
        {
          bg: "#fe8163",
          before: "#A5E6BA",
        },
        {
          bg: "#c88a38",
          before: "#A5E6BA",
        },
        {
          bg: "#74c69d",
        },
        {
          bg: "#e5989b",
        },
        {
          bg: "#6b77ff",
        },
      ],
      indexColor: 0,
    };
  },
  methods: {
    next() {
      if (this.indexColor < this.colors.length - 1) {
        this.indexColor++;
      } else {
        this.indexColor = 0;
      }
      document.getElementById("maintitle").className = "animate-title";
      setTimeout(() => {
        document.getElementById("maintitle").classList.remove("animate-title");
      }, 800);
      setTimeout(() => {
        document.querySelector(".container").style.backgroundColor =
          this.colors[this.indexColor].bg;
      }, 500);
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Londrina+Solid:wght@100;300;400;900&display=swap");
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
a {
  text-decoration: none;
}

#nav {
  padding: 30px;
  display: flex;
  justify-content: flex-end;
  width: 80%;

  a {
    font-weight: bold;
    color: #f1f2f0;
    font-size: 36px;
    font-family: "Londrina Solid", cursive;
    margin-left: 50px;
    text-decoration: none;

    transition: 0.3s ease-in-out;
    &::before {
      content: "";
      position: absolute;
      bottom: 0px;
      left: 50%;
      transform: translateX(-50%);

      width: calc(100% + 20px);
      height: 30px;
      background-color: #382530;
      z-index: -1;

      opacity: 0;

      transition: all 0.5s ease-in-out;
    }
    &:hover {
      color: #382530;
      transform: rotate(5deg);
    }

    &.router-link-exact-active {
      position: relative;
      z-index: 2;

      &::before {
        opacity: 1;
      }
      &:hover {
        color: #f1f2f0;
        transform: none;
        &::before {
          transform: translateX(-50%) rotate(5deg);
        }
      }
    }
  }
}
body {
  margin: 0;
}
.container {
  width: 100%;
  height: 100vh;

  background: #fe8163;
  position: relative;

  overflow: hidden;
}
.center {
  max-width: 1600px;
  margin: 0 auto;
  padding: 70px 50px;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
