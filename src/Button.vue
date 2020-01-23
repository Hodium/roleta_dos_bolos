<template>
  <div :id="buttonId" :class="getContainerClass()" @click="buttonPressed">
    <img v-show="roulette" class="regularImage" src="./assets/btn3.svg" />
    <img v-show="min_size" class="irregularImage" src="./assets/btn2.svg" />
    <img v-show="!pressed && !roulette && !min_size" class="regularImage" src="./assets/btn.svg" />
    <img v-show="pressed && !roulette && !min_size" class="regularImage" src="./assets/btn4.svg" />
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
    roulette: Boolean,
    buttonId: String,
    name: String,
    min_size: Boolean
  },
  methods: {
    buttonPressed() {
      this.pressed = !this.pressed;
      this.$emit("buttonPressed", this.buttonId);
    },
    getContainerClass() {
      if (this.buttonId.indexOf("r") == 0) return "containerRou";
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
