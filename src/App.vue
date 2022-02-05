<template>
  <div id="app">
    <div v-show="mainScreen" @click="advanceToMenu" class="mainScreen">
      <img class="mainScreenImage" src="./assets/logo.svg" />
    </div>
    <div v-show="menuScreen" class="menuScreen">
      <div>
        <img class="imageMenuScreen" src="./assets/logo.svg" />
        <Button buttonId="m1" name="SORTEIO DE DOMINGO" :menu="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="m2" name="LISTA DE COMPRAS" :menu="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="m3" name="CALENDÁRIO" :menu="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="m4" name="MURAL DA VERGONHA" :menu="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="m5" name="LISTA DOS BOLOS" :menu="true" @buttonPressed="buttonPressed"></Button>
      </div>
      <div class="footerFixedWhite">
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
    <div v-show="pickingScreen" class="otherScreen">
      <img src="./assets/logoTop.svg" class="otherScreenTop" @click="goHome" />
      <img src="./assets/logo.svg" class="otherScreenTopLogo" @click="goHome" />
      <h3>ESCOLHE OS PRATOS:</h3>
      <div class="alignCenterVertical">
        <Button buttonId="p1" name="CACHORROS" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="p2"
          name="ESPARGUETE À BOLONHESA"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="p3"
          name="ESPARUETE À CARBONARA"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="p4" name="HAMBÚRGUER" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="p5" name="MASSA COM ATUM" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="p6" name="FRANGO ASSADO" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="p7"
          name="MASSA COM NATAS E SALSICHAS"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="p8" name="WRAPS" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="p9" name="LASANHA" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="p10"
          name="BIFINHOS COM NATAS"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="p11" name="PICA-PAU" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="p12" name="FRANGO À BRAZ" :regular="true" @buttonPressed="buttonPressed"></Button>
      </div>
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
        <Button buttonId="t4" name="LEVANTAR A MESA" :regular="true" @buttonPressed="buttonPressed"></Button>
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
        <Button buttonId="c1" name="CARMEN MARTINS" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c2" name="PEDRO OLIVEIRA" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c3" name="PATRÍCIA NEVES" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c4" name="PEDRO SARDINHA" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c5" name="MIGUEL CASTELA" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c6" name="RAFAELA ROSA" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c7" name="SOFIA COTRIM" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c8" name="JOSÉ POMBO" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c9" name="RUI COTRIM" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="c10"
          name="CATARINA SANTOS"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button
          buttonId="c11"
          name="ALESSANDRO GUZZO"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="c12" name="TERESA GUIOMAR" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="c13"
          name="FILIPE FERNANDES"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="c14" name="JOANA LOPES" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button
          buttonId="c15"
          name="RODRIGO TEIXEIRA"
          :regular="true"
          @buttonPressed="buttonPressed"
        ></Button>
        <Button buttonId="c16" name="ANDRÉ ROLIZ" :regular="true" @buttonPressed="buttonPressed"></Button>
        <Button buttonId="c17" name="MARIANA AMARO" :regular="true" @buttonPressed="buttonPressed"></Button>
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
      <div class="centered titleAndRoulette">
        <h3>DESCOBRE A TUA TAREFA DE DOMINGO!</h3>
        <h5>QUE A SORTE ESTEJA CONTIGO.</h5>
        <img class="roulette" src="./assets/roulette.gif" />
      </div>
      <div class="footerFixed">
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
    <div v-show="resultsScreen" class="otherScreen" :key="resultsComponentKey">
      <img src="./assets/logoTop.svg" class="otherScreenTop" @click="goHome" />
      <img src="./assets/logo.svg" class="otherScreenTopLogo" @click="goHome" />
      <Job type="plate" class="firstResult" :winner="getResult('plate')" />
      <Job type="shop" :winner="getResult('t1')" />
      <Job type="meals" :winner="getResult('t2')" />
      <Job type="settable" :winner="getResult('t3')" />
      <Job type="cleartable" :winner="getResult('t4')" />
      <Job type="dishes" :winner="getResult('t5')" />
      <Job type="mop" :winner="getResult('t6')" />
      <Job type="dry" :winner="getResult('t7')" />
      <Job type="trash" :winner="getResult('t8')" />
      <Job type="lucky" :winner="getResult('t9')" />
      <div class="footer">
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "./Button";
import Job from "./Job";
import results from "./results.json";
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
      adminMode: true,
      mainScreen: true,
      menuScreen: false,
      pickingScreen: false,
      waitingScreen: false,
      resultsScreen: false,
      cakes: [],
      tasks: [],
      plates: [],
      resultList: {},
      resultsComponentKey: 0
    };
  },
  methods: {
    advanceToMenu() {
      this.mainScreen = false;
      this.menuScreen = true;
    },
    buttonPressed(id, name) {
      if (id.includes("c")) this.cakeButton(name);
      else if (id.includes("t")) this.taskButton(id);
      else if (id.includes("p")) this.plateButton(name);
      else if (id.includes("m")) this.menuButton(id);
      else this.rouletteButton();
    },
    cakeButton(name) {
      var index = this.cakes.indexOf(name);
      if (index != -1) this.cakes.splice(name, 1);
      else this.cakes.push(name);
    },
    getCurrentResultsLists() {
      var currResults = results;
      var auxPlatesLists = currResults.plates;
      var auxCakesLists = currResults.cakes;
      var finalPlatesLists = [];
      var finalCakesLists = [];

      //plates
      if (auxPlatesLists.length == 0) finalPlatesLists = this.plates;
      else {
        auxPlatesLists.sort((a, b) => {
          return parseInt(a.id) > parseInt(b.id);
        });
        var readyPlates = false;
        auxPlatesLists.forEach(list => {
          if (!readyPlates) {
            list.values.forEach(listItem => {
              if (this.plates.indexOf(listItem) >= 0) {
                finalPlatesLists.push(listItem);
              }
            });
          }
          if (finalPlatesLists.length != 0) readyPlates = true;
        });
      }

      //cakes
      if (auxCakesLists.length == 0) finalCakesLists.push(this.cakes);
      else {
        auxCakesLists.sort((a, b) => {
          return parseInt(a.id) > parseInt(b.id);
        });
        var totalIndex = 0;
        auxCakesLists.forEach(list => {
          if (totalIndex != this.cakes.length) {
            var subList = [];
            list.values.forEach(listItem => {
              if (this.cakes.indexOf(listItem) >= 0) {
                subList.push(listItem);
                totalIndex++;
              }
            });
            finalCakesLists.push(subList);
          }
        });
      }
      return { platesList: finalPlatesLists, cakesList: finalCakesLists };
    },
    getResult(id) {
      return this.resultList[id];
    },
    goHome() {
      this.mainScreen = true;
      this.menuScreen = false;
      this.pickingScreen = false;
      this.waitingScreen = false;
      this.resultsScreen = false;
    },
    menuButton(id) {
      this.menuScreen = false;
      switch (id) {
        case "m1":
          if (this.adminMode) this.pickingScreen = true;
          else this.rouletteButton();
          break;
        case "m2":
        case "m3":
        case "m4":
        case "m5":
          this.menuScreen = true;
          break;
      }
    },
    plateButton(name) {
      var index = this.plates.indexOf(name);
      if (index != -1) this.plates.splice(name, 1);
      else this.plates.push(name);
    },
    resultButton() {
      this.waitingScreen = false;
      this.resultsScreen = true;
    },
    rouletteButton() {
      this.pickingScreen = false;
      this.waitingScreen = true;
      if (this.adminMode) this.spinTheRoulette();
      var that = this;
      setTimeout(function() {
        that.resultButton();
        this.resultsComponentKey++;
      }, 3000);
    },
    spinTheRoulette() {
      var auxLists = this.getCurrentResultsLists();

      //plates
      var auxPlateIndex = Math.floor(
        Math.random() * auxLists.platesList.length
      );
      this.resultList["plate"] = auxLists.platesList[auxPlateIndex];

      //cakes
      var auxLuckyCake = "";
      var auxTasks = [...this.tasks];
      auxLists.cakesList.forEach(cakeList => {
        cakeList.forEach(cakeItem => {
          if (auxTasks.length > 0) {
            var index = Math.floor(Math.random() * auxTasks.length);
            this.resultList[auxTasks[index]] = cakeItem;
            auxTasks.splice(index, 1);
          } else auxLuckyCake += cakeItem + "\r\n";
        });
      });
      auxLuckyCake = auxLuckyCake.substring(0, auxLuckyCake.length - 1);
      this.resultList["t9"] = auxLuckyCake;

      var finalResult = this.updateResults()
      prompt("SALVA ESTA RESPOSTA!", finalResult)
    },
    taskButton(id) {
      var index = this.tasks.indexOf(id);
      if (index != -1) this.tasks.splice(id, 1);
      else this.tasks.push(id);
    },
    updateResults(){
      //TODO - Update ao documento results      
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

.roulette {
  margin-top: 50px;
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
  align-items: center;
}

.mainScreenImage{
width: inherit;
height: fit-content;
padding: 1em;
}

.menuScreen {
  position: fixed;
  margin: 0;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: url("./assets/bck.svg");
  background-repeat: no-repeat;
  background-size: auto;
  overflow: auto;
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

.titleAndRoulette {
  margin-top: 10%;
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
