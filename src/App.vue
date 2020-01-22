<template>
  <div id="app">
    <div v-show="zeroJanela" @click="avancarPrimeiraJanela" class="zeroJanela">
      <img src="./assets/logo.svg" />
    </div>
    <div v-show="primeiraJanela" class="primeiraJanela">
      <img src="./assets/logoTop.svg" class="primeiraJanelaTop" />
      <img src="./assets/logo.svg" class="primeiraJanelaTopLogo" />
      <h3>ESCOLHE AS TAREFAS:</h3>
      <div class="tarefasTodas">
        <Button
          buttonId="t1"
          name="IR ÀS COMPRAS"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="t2"
          name="PREPARAR AS REFEIÇÔES"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="t3"
          name="PÔR A MESA"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="t4"
          name="LEVANTAR A MESA"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="t5"
          name="LAVAR A LOIÇA"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <div class="tarefasOpcionais">
          <Button
            buttonId="t6"
            name="VARRER O CHÃO"
            :min_size="true"
            @carregueiNoBotao="carregueiNoBotao"
          ></Button>
          <Button
            buttonId="t7"
            name="SECAR A LOIÇA"
            :min_size="true"
            @carregueiNoBotao="carregueiNoBotao"
          ></Button>
          <Button
            buttonId="t8"
            name="LEVAR O LIXO"
            :min_size="true"
            @carregueiNoBotao="carregueiNoBotao"
          ></Button>
        </div>
      </div>
      <h3>ESCOLHE OS BOLOS:</h3>
      <div class="tarefasTodas">
        <Button
          buttonId="p1"
          name="CARMEN MARTINS"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p2"
          name="PEDRO OLIVEIRA"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p3"
          name="PATRÍCIA NEVES"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p4"
          name="PEDRO SARDINHA"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p5"
          name="MIGUEL CASTELA"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p6"
          name="RAFAELA ROSA"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p7"
          name="SOFIA COTRIM SANTOS"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p8"
          name="OSÉ MIGUEL POMBO"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p9"
          name="RUI COTRIM SANTOS"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p10"
          name="CATARINA SANTOS"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p11"
          name="ALESSANDRO GUZZO"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p12"
          name="TERESA GUIOMAR"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p13"
          name="FILIPE FERNANDES"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p14"
          name="JOANA LOPES"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <Button
          buttonId="p15"
          name="RODRIGO TEIXEIRA"
          :min_size="false"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
      </div>
      <div class="tarefasTodas">
        <Button
          buttonId="r1"
          name="ROLETA DA SORTE"
          :min_size="false"
          :roulette="true"
          @carregueiNoBotao="carregueiNoBotao"
        ></Button>
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
    <div v-show="segundaJanela" class="segundaJanela">
      <img src="./assets/logoTop.svg" class="primeiraJanelaTop" />
      <img src="./assets/logo.svg" class="primeiraJanelaTopLogo" />
      <div class="centrado">
        <h3>DESCOBRE A TUA TAREFA DE DOMINGO!</h3>
        <h5>QUE A SORTE ESTEJA CONTIGO.</h5>
        <img id="imageDaRoleta" src="./assets/roulette.png" />
      </div>
      <Button
        buttonId="v1"
        name="RESULTADOS"
        :min_size="false"
        @carregueiNoBotao="carregueiNoBotao"
      ></Button>
    </div>
    <div v-show="terceiraJanela">
      <h1>Ah! Rólêta dus Bólòs</h1>
      <h3>SORTUDO1:</h3>
      <h5>PEDRO</h5>
      <h3>SORTUDO2:</h3>
      <h5>CARMEN</h5>
    </div>
  </div>
</template>

<script>
import Button from "./Button";
export default {
  name: "app",
  components: {
    Button
  },
  data() {
    return {
      zeroJanela: false,
      primeiraJanela: true,
      segundaJanela: false,
      terceiraJanela: false,
      participantes: [],
      tarefas: []
    };
  },
  methods: {
    avancarPrimeiraJanela() {
      this.zeroJanela = false;
      this.primeiraJanela = true;
    },
    carregueiNoBotao(id) {
      if (id.includes("p")) this.botaoParticipante(id);
      else if (id.includes("t")) this.botaoTarefa(id);
      else if (id.includes("v")) this.botaoResultados(id);
      else this.botaoRoleta();
    },
    botaoParticipante(id) {
      var index = this.participantes.indexOf(id);
      if (index != -1) this.participantes.splice(id, 1);
      else this.participantes.push(id);
    },
    botaoTarefa(id) {
      var index = this.tarefas.indexOf(id);
      if (index != -1) this.tarefas.splice(id, 1);
      else this.tarefas.push(id);
    },
    botaoResultados() {
      this.segundaJanela = false;
      this.terceiraJanela = true;
    },
    botaoRoleta() {
      this.primeiraJanela = false;
      this.segundaJanela = true;
      this.rodarRoleta();
      // while (this.segundaJanela) {
        // var img = document.getElementById("imageDaRoleta");
        // img.style.transform = "rotate(90deg)";
      // }
    },
    rodarRoleta() {}
  }
};
</script>

<style>
@font-face {
  font-family: Roboto;
  src: url("./assets/Roboto-Light.ttf");
}

* {
  font-family: "Roboto", sans-serif;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

body {
  margin: 0;
  height: 100%;
}

.zeroJanela {
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

.primeiraJanela {
  background-color: #eff3fc;
}

.primeiraJanelaTop {
  position: absolute;
  top: 0;
}

.primeiraJanelaTopLogo {
  position: relative;
  top: 0;
  width: 45%;
  left: 30%;
  margin-top: 5%;
}

.segundaJanela {
  position: fixed;
  margin: 0;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-repeat: no-repeat;
  background-size: auto;
  background-color: #eff3fc;
}

.centrado {
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

h5{
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

.tarefasTodas {
  display: grid;
  justify-content: center;
}

.tarefasOpcionais {
  display: flex;
}

.tarefaOpcionalBotao {
  float: left;
}

.botaoRoleta {
  color: #e3e3e3;
}
</style>
