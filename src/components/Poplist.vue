<template>
  <div class="listContainer">
    <ul>
      <li class="elipseContainer eli-co1">
        <span>1</span>
        <h2 v-html="top3list[0].name"></h2>
        <div class="imgContainer imgContainer1">
          <img class="picture1 picture" :src="top3list[0].img" />
        </div>
      </li>
      <li class="elipseContainer eli-co2">
        <span>2</span>
        <h2>{{ top3list[1].name }}</h2>
        <div class="imgContainer imgContainer2">
          <img class="picture2 picture" :src="top3list[1].img" />
        </div>
      </li>
      <li class="elipseContainer eli-co3">
        <span>3</span>
        <h2>{{ top3list[2].name }}</h2>
        <div class="imgContainer imgContainer3">
          <img class="picture3 picture" :src="top3list[2].img" />
        </div>
      </li>
    </ul>
    <svg viewBox="0 0 475 443">
      <defs>
        <clipPath id="elipse-svg1">
          <path
            d="M475 189.604C475 311.935 343.479 443 221.273 443C99.0674 443 0 343.831 0 221.5C0 99.1689 99.0674 0 221.273 0C343.479 0 475 67.2729 475 189.604Z"
            fill="white"
          />
        </clipPath>
      </defs>
    </svg>
    <svg viewBox="0 0 379 365">
      <defs>
        <clipPath id="elipse-svg2">
          <path
            d="M378.5 154.5C378.5 255.292 313.292 365 212.5 365C111.708 365 0.5 283.292 0.5 182.5C0.5 81.708 111.708 0 212.5 0C313.292 0 378.5 53.708 378.5 154.5Z"
            fill="#F1F2F0"
          />
        </clipPath>
      </defs>
    </svg>
    <svg viewBox="0 0 271 267">
      <defs>
        <clipPath id="elipse-svg3">
          <path
            d="M271 135.5C271 210.335 232.335 267 157.5 267C82.6654 267 0 210.335 0 135.5C0 60.6654 60.6654 0 135.5 0C210.335 0 271 60.6654 271 135.5Z"
            fill="white"
          />
        </clipPath>
      </defs>
    </svg>
  </div>
</template>

<script>
export default {
  name: "Poplist",
  props: ["top3list"],
  data() {
    return {};
  },
};
</script>

<style lang="scss">
.picture {
  aspect-ratio: 1 / 1;
  object-fit: cover;
  mix-blend-mode: luminosity;
}
.picture1 {
  clip-path: url(#elipse-svg1);
  width: 475px;
}
.picture2 {
  clip-path: url(#elipse-svg2);
  width: 379px;
}
.picture3 {
  clip-path: url(#elipse-svg3);
  width: 271px;
}
svg {
  width: 0;
  height: 0;
}
.listContainer {
  width: 100%;
  padding-top: 70px;
  ul {
    width: 100%;
    display: flex;
    justify-content: space-around;
    list-style: none;
    li {
      position: relative;
      height: fit-content;

      &::before {
        position: absolute;
        content: "";
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 10;

        opacity: 0.1;
      }

      &:hover {
        h2 {
          opacity: 1;
        }
        .picture {
          mix-blend-mode: normal;
          animation-play-state: paused;
          filter: none;
        }
      }
      span {
        position: absolute;
        font-size: 160px;
        color: #382530;
        font-family: "Londrina Solid", cursive;
        bottom: -30px;
        left: 30px;
        z-index: 2;
      }
      h2 {
        position: absolute;
        font-size: 80px;
        color: #f1f2f0;
        text-transform: uppercase;
        font-family: "Londrina Solid", cursive;
        bottom: -30px;
        left: 100px;
        z-index: 1;
        margin: 0;
        line-height: 70px;
        min-height: 140px;

        transition: 0.5s ease-in-out;

        opacity: 0;

        display: flex;
        align-items: center;
        justify-content: flex-start;
      }
      .elipse {
        &:hover {
          animation-play-state: paused;
        }
      }
    }
    .eli1 {
      width: 500px;
      animation: circlemove 12s linear infinite;
    }
    .eli2 {
      padding-top: 80px;
    }

    .eli-co1 {
      span {
        animation: circlemoveAlt 12s linear infinite;
      }
    }
    .eli-co2 {
      span {
        font-size: 120px;
        animation: circlemove 12s linear infinite;
      }
    }
    .eli-co3 {
      span {
        font-size: 100px;
        animation: circlemove--small 12s linear infinite;
      }
    }
  }
  .picture {
    overflow: hidden;
    transition: all 0.3s ease-in-out;
    position: relative;
    filter: blur(10px);
  }
}
</style>