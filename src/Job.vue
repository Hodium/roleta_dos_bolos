<template>
  <div class="container">
    <img v-show="type != 'lucky'" class="base" src="./assets/jobButton.svg" />
    <img v-show="type == 'lucky'" class="base" src="./assets/jobButtonLarge.svg" />

    <img v-if="type == 'plate'" class="top0" src="./assets/plate.svg" />
    <img v-if="type == 'shop'" class="top1" src="./assets/shop.svg" />
    <img v-if="type == 'meals'" class="top2" src="./assets/meals.svg" />
    <img v-if="type == 'settable'" class="top3" src="./assets/settable.svg" />
    <img v-if="type == 'cleartable'" class="top4" src="./assets/cleartable.svg" />
    <img v-if="type == 'dishes'" class="top5" src="./assets/dishes.svg" />
    <img v-if="type == 'mop'" class="top6" src="./assets/mop.svg" />
    <img v-if="type == 'dry'" class="top7" src="./assets/dry.svg" />
    <img v-if="type == 'trash'" class="top8" src="./assets/trash.svg" />
    <img v-if="type == 'lucky'" class="top9" src="./assets/lucky.svg" />

    <div :class="getCenteredClass()">{{getTask(type)}}</div>
    <div :class="getCenteredMiddleClass()">
      <hr />
    </div>
    <div :class="getCenteredBottomClass()">
      <label>{{winner}}</label>
    </div>
  </div>
</template>

<script>
export default {
  name: "Job",
  props: {
    type: String,
    winner: String
  },
  methods: {
    getCenteredBottomClass() {
      if (this.type == "lucky") return "centeredBottomLucky";
      else return "centeredBottom";
    },
    getCenteredClass() {
      if (this.type == "lucky") return "centeredLucky";
      else return "centered";
    },
    getCenteredMiddleClass() {
      if (this.type == "lucky") return "centeredMiddleLucky";
      else return "centeredMiddle";
    },
    getTask(type) {
      switch (type) {
        case "plate":
          return "PRATO";
        case "shop":
          return "IR ÀS COMPRAS";
        case "meals":
          return "PREPARAR AS REFEIÇÕES";
        case "settable":
          return "PÔR A MESA";
        case "cleartable":
          return "LEVANTAR A MESA";
        case "dishes":
          return "LAVAR A LOIÇA";
        case "mop":
          return "VARRER O CHÃO";
        case "dry":
          return "SECAR A LOIÇA";
        case "trash":
          return "LEVAR O LIXO";
        case "lucky":
          return "HOJE É O TEU DIA DE SORTE";
      }
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

.container {
  position: relative;
  text-align: center;
  top: 0;
  left: 0;
}

.base {
  position: relative;
  top: 0;
  left: 0;
}

.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-top: 50px;
  font-size: 15px;
  width: fit-content;
}

.centeredLucky {
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-top: 50px;
  font-size: 15px;
  width: fit-content;
}

.centeredMiddle {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-top: 70px;
}

.centeredMiddleLucky {
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-top: 70px;
}

hr {
  width: 220px;
  opacity: 0.2;
}

.centeredBottom {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-top: 110px;
  width: fit-content;
  font-size: 19px;
}

.centeredBottomLucky {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-top: 110px;
  font-size: 19px;
}

.top0 {
  position: absolute;
  transform: translate(-135%, 20%);
}

.top1,
.top7 {
  position: absolute;
  transform: translate(-190%, 45%);
}

.top2,
.top3,
.top4,
.top6 {
  position: absolute;
  transform: translate(-155%, 45%);
}

.top5 {
  position: absolute;
  transform: translate(-135%, 20%)
}

.top8 {
  position: absolute;
  transform: translate(-130%, 45%);
}

.top9 {
  position: absolute;
  transform: translate(-165%, 45%);
}
</style>
