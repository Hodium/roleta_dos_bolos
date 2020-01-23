<template>
  <div :id="buttonId" :class="getContainerClass()" @click="buttonPressed">
    <img v-show="menu" class="regularImage" src="./assets/menuBtn.svg" />
    <img v-show="roulette" class="regularImage" src="./assets/rouletteBtn.svg" />
    <img v-show="min_size && !pressed" class="irregularImage" src="./assets/smallBtn.svg" />
    <img v-show="min_size && pressed" class="irregularImage" src="./assets/smallBtnPressed.svg" />
    <img v-show="regular && !pressed" class="regularImage" src="./assets/regularBtn.svg" />
    <img v-show="regular && pressed" class="regularImage" src="./assets/regularBtnPressed.svg" />
    <div v-show="!min_size" class="centered">{{name}}</div>
    <div v-show="min_size" class="centeredMin">{{name}}</div>
  </div>
</template>

<script>
export default {
  name: "Button",
  data() {
    return {
      pressed: false
    };
  },
  props: {
    menu: Boolean,
    regular: Boolean,
    roulette: Boolean,
    min_size: Boolean,
    buttonId: String,
    name: String
  },
  methods: {
    buttonPressed() {
      this.pressed = !this.pressed;
      this.$emit("buttonPressed", this.buttonId);
    },
    getContainerClass() {
      if (this.buttonId.indexOf("r") == 0 || this.buttonId.indexOf("m") == 0)
        return "containerRou";
      else return "container";
    }
  }
};
</script>

<style scoped>
@font-face {
  font-family: Roboto;
  src: url("./assets/Roboto-Light.ttf");
}

* {
  font-family: "Roboto", sans-serif;
  -webkit-user-select: none;
  -webkit-touch-callout: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

body {
  margin: 0;
  height: 100%;
}

*:focus {
  outline: 0;
  outline: none;
}

.regularImage {
  margin: -2%;
}

.irregularImage {
  margin: -5%;
  width: 110px;
}

.container {
  position: relative;
  text-align: center;
  color: #666666;
}

.containerRou {
  position: relative;
  text-align: center;
  color: #e3e3e3;
  font-weight: bold;
}

.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: fit-content;
}

.centeredMin {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 13px;
  word-wrap: break-word;
}
</style>
