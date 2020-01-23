<template>
  <div id="app">
    <div v-show="mainScreen" @click="advanceToMenu" class="mainScreen">
      <img src="./assets/logo.svg" />
    </div>
    <div v-show="menuScreen" class="mainScreen">
      <div>
        <img class="imageMenuScreen" src="./assets/logo.svg" />
        <Button
          buttonId="m1"
          name="SORTEIO DE DOMINGO"
          :menu="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="m2"
          name="LISTA DE COMPRAS"
          :menu="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="m3"
          name="CALENDÁRIO"
          :menu="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="m4"
          name="MURAL DA VERGONHA"
          :menu="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="m5"
          name="LISTA DOS BOLOS"
          :menu="true"
          @buttonPressed="buttonPressed"
        ></Button>
      </div>
      <div class="footerFixedWhite">
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
    <div v-show="pickingScreen" class="otherScreen">
      <img src="./assets/logoTop.svg" class="otherScreenTop" @click="goHome" />
      <img src="./assets/logo.svg" class="otherScreenTopLogo" @click="goHome" />
      <h3>ESCOLHE AS TAREFAS:</h3>
      <div class="alignCenterVertical">
        <Button buttonId="t1" name="IR ÀS COMPRAS" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="t2"
          name="PREPARAR AS REFEIÇÔES"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="t3" name="PÔR A MESA" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="t4"
          name="LEVANTAR A MESA"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="t5" name="LAVAR A LOIÇA" :regular="true" @buttonPressed="buttonPressed"></Button>
        <div class="optionalTasks">
          <Button
            buttonId="t6"
            name="VARRER O CHÃO"
            :min_size="true"
            @buttonPressed="buttonPressed"
          ></Button>
          <Button
            buttonId="t7"
            name="SECAR A LOIÇA"
            :min_size="true"
            @buttonPressed="buttonPressed"
          ></Button>
          <Button buttonId="t8" name="LEVAR O LIXO" :min_size="true" @buttonPressed="buttonPressed"></Button>
        </div>
      </div>
      <h3>ESCOLHE OS BOLOS:</h3>
      <div class="alignCenterVertical">
        <Button
          buttonId="p1"
          name="CARMEN MARTINS"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p2"
          name="PEDRO OLIVEIRA"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p3"
          name="PATRÍCIA NEVES"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p4"
          name="PEDRO SARDINHA"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p5"
          name="MIGUEL CASTELA"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="p6" name="RAFAELA ROSA" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="p7"
          name="SOFIA COTRIM SANTOS"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p8"
          name="OSÉ MIGUEL POMBO"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p9"
          name="RUI COTRIM SANTOS"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p10"
          name="CATARINA SANTOS"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p11"
          name="ALESSANDRO GUZZO"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p12"
          name="TERESA GUIOMAR"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p13"
          name="FILIPE FERNANDES"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="p14" name="JOANA LOPES" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="p15"
          name="RODRIGO TEIXEIRA"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="p16" name="ANDRÉ ROLIZ" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="p17"
          name="MARIANA AMARAO"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
      </div>
      <div class="alignCenterVertical">
        <Button
          buttonId="r1"
          name="ROLETA DA SORTE"
          :roulette="true"
          @buttonPressed="buttonPressed"
        ></Button>
      </div>
      <div class="footer">
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
    <div v-show="waitingScreen" class="otherScreen">
      <img src="./assets/logoTop.svg" class="otherScreenTop" @click="goHome" />
      <img src="./assets/logo.svg" class="otherScreenTopLogo" @click="goHome" />
      <div class="centered">
        <h3>DESCOBRE A TUA TAREFA DE DOMINGO!</h3>
        <h5>QUE A SORTE ESTEJA CONTIGO.</h5>
        <img src="./assets/roulette.gif" />
      </div>
      <div class="footerFixed">
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
    <div v-show="resultsScreen" class="otherScreen">
      <img src="./assets/logoTop.svg" class="otherScreenTop" @click="goHome" />
      <img src="./assets/logo.svg" class="otherScreenTopLogo" @click="goHome" />
      <Job type="plate" class="firstResult" winner="TESTE NOME" />
      <Job type="shop" winner="TESTE NOME" />
      <Job type="meals" winner="TESTE NOME" />
      <Job type="settable" winner="TESTE NOME" />
      <Job type="cleartable" winner="TESTE NOME" />
      <Job type="dishes" winner="TESTE NOME" />
      <Job type="mop" winner="TESTE NOME" />
      <Job type="dry" winner="TESTE NOME" />
      <Job type="trash" winner="TESTE NOME" />
      <Job type="lucky" winner="TESTE NOME" />
      <div class="footer">
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "./Button";
import Job from "./Job";
export default {
  name: "app",
  components: {
    Button,
    Job
  },
  created() {
    document.addEventListener("contextmenu", function(e) {
      e.preventDefault();
    });
  },
  data() {
    return {
      mainScreen: true,
      menuScreen: false,
      pickingScreen: false,
      waitingScreen: false,
      resultsScreen: false,
      cakes: [],
      tasks: []
    };
  },
  methods: {
    advanceToMenu() {
      this.mainScreen = false;
      this.menuScreen = true;
    },
    buttonPressed(id) {
      if (id.includes("p")) this.cakeButton(id);
      else if (id.includes("t")) this.taskButton(id);
      else if (id.includes("m")) this.menuButton(id);
      else this.rouletteButton();
    },
    menuButton(id) {
      this.menuScreen = false;
      switch (id) {
        case "m1":
          this.pickingScreen = true;
          break;
        case "m2":
        case "m3":
        case "m4":
        case "m5":
          this.menuScreen = true;
          break;
      }
    },
    cakeButton(id) {
      var index = this.cakes.indexOf(id);
      if (index != -1) this.cakes.splice(id, 1);
      else this.cakes.push(id);
    },
    goHome() {
      return;
      // this.mainScreen = true;
      // this.pickingScreen = false;
      // this.waitingScreen = false;
      // this.resultsScreen = false;
    },
    resultButton() {
      this.waitingScreen = false;
      this.resultsScreen = true;
    },
    rouletteButton() {
      this.pickingScreen = false;
      this.waitingScreen = true;
      this.spinTheRoulette();
      var that = this;
      setTimeout(function() {
        that.resultButton();
      }, 3000);
    },
    spinTheRoulette() {
      this.tasks.forEach(() => {
        //TODO
      });
    },
    taskButton(id) {
      var index = this.tasks.indexOf(id);
      if (index != -1) this.tasks.splice(id, 1);
      else this.tasks.push(id);
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

.mainScreen {
  position: fixed;
  margin: 0;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: url("./assets/bck.svg");
  background-repeat: no-repeat;
  background-size: auto;
  display: flex;
  justify-content: center;
}

.otherScreen {
  position: fixed;
  margin: 0;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-color: #eff3fc;
  background-repeat: no-repeat;
  background-size: auto;
  overflow: auto;
}

.otherScreenTop {
  position: absolute;
  top: 0;
  width: 100%;
}

.otherScreenTopLogo {
  position: relative;
  top: 0;
  width: 45%;
  left: 30%;
  margin-top: 5%;
}

.imageMenuScreen {
  margin-left: 12%;
  margin-top: 10%;
  margin-bottom: 20%;
}

.centered {
  display: grid;
  justify-content: center;
  margin-bottom: 5%;
}

h3 {
  display: flex;
  font-size: 13px;
  color: #666666;
  margin-left: 10%;
  margin-top: 15%;
}

h5 {
  display: flex;
  font-size: 13px;
  color: #666666;
  margin-top: -5%;
  margin-left: 18%;
}

.container {
  position: relative;
  text-align: center;
  color: #666666;
}

.container:hover {
  cursor: pointer;
}

.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.centeredMin {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

label {
  font-size: 10px;
  text-align: center;
}

.alignCenterVertical {
  display: grid;
  justify-content: center;
}

.footerFixedWhite {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  text-align: center;
  color: #ffffff;
}

.footerFixed {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  text-align: center;
  color: #666666;
}

.footer {
  left: 0;
  bottom: 0;
  width: 100%;
  text-align: center;
  color: #666666;
}

.optionalTasks {
  display: flex;
  justify-content: center;
}

.rouletteButton {
  color: #e3e3e3;
}

.firstResult {
  margin-top: 60px;
}
</style>
