<template>
  <div :id="buttonId" :class="getContainerClass()" @click="carregueiNoBotao">
    <img v-show="roulette" class="imagemNormal" src="./assets/btn3.svg" />
    <img v-show="min_size" class="imagemAnormal" src="./assets/btn2.svg" /> 
    <img v-show="!pressed && !roulette && !min_size" class="imagemNormal" src="./assets/btn.svg" />
    <img v-show="pressed && !roulette && !min_size" class="imagemNormal" src="./assets/btn4.svg" />
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
    carregueiNoBotao() {
      this.pressed = !this.pressed;
      this.$emit("carregueiNoBotao", this.buttonId);
    },
    getContainerClass() {
      if (this.buttonId.indexOf("r") == 0) return "containerRou";
      else return "container";
    }
  }
};
</script>

<style>
*:focus {
  outline: 0;
  outline: none;
}

.imagemNormal {
  margin: -2%;
}

.imagemAnormal {
  margin: -2%;
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
  width: fit-content
}

.centeredMin {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 13px;
  word-wrap: break-word
}
</style>
