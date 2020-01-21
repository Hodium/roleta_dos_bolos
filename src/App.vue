<template>
  <div id="app">
    <div v-show="primeiraJanela">
      <h1>Ah! Rólêta dus Bólòs</h1>
      <h3>ESCOLHE AS TAREFAS:</h3>
      <div class="tarefasTodas">
        <button id="t1" class="botao" @click="carregueiNumBotao">IR ÀS COMPRAS</button>
        <button id="t2" class="botao" @click="carregueiNumBotao">PREPARAR A REFEIÇÃO</button>
        <button id="t3" class="botao" @click="carregueiNumBotao">PÔR A MESA</button>
        <button id="t4" class="botao" @click="carregueiNumBotao">LEVANTAR A MESA</button>
        <button id="t5" class="botao" @click="carregueiNumBotao">LAVAR A LOIÇA</button>
        <div class="tarefasOpcionais">
          <button id="t6" class="botao tarefaOpcionalBotao" @click="carregueiNumBotao">VARRER O CHÃO</button>
          <button id="t7" class="botao tarefaOpcionalBotao" @click="carregueiNumBotao">SECAR A LOIÇA</button>
          <button id="t8" class="botao tarefaOpcionalBotao" @click="carregueiNumBotao">LEVAR O LIXO</button>
        </div>
      </div>
      <h3>ESCOLHE OS BOLOS:</h3>
      <div class="tarefasTodas">
        <button id="p1" class="botao" @click="carregueiNumBotao">CARMEN MARTINS</button>
        <button id="p2" class="botao" @click="carregueiNumBotao">PEDRO OLIVEIRA</button>
        <button id="p3" class="botao" @click="carregueiNumBotao">PATRÍCIA NEVES</button>
        <button id="p4" class="botao" @click="carregueiNumBotao">PEDRO SARDINHA</button>
        <button id="p5" class="botao" @click="carregueiNumBotao">MIGUEL CASTELA</button>
        <button id="p6" class="botao" @click="carregueiNumBotao">RAFAELA ROSA</button>
        <button id="p7" class="botao" @click="carregueiNumBotao">SOFIA COTRIM SANTOS</button>
        <button id="p8" class="botao" @click="carregueiNumBotao">JOSÉ MIGUEL POMBO</button>
        <button id="p9" class="botao" @click="carregueiNumBotao">RUI COTRIM SANTOS</button>
        <button id="p10" class="botao" @click="carregueiNumBotao">CATARINA SANTOS</button>
        <button id="p11" class="botao" @click="carregueiNumBotao">ALESSANDRO GUZZO</button>
        <button id="p12" class="botao" @click="carregueiNumBotao">TERESA GUIOMAR</button>
        <button id="p13" class="botao" @click="carregueiNumBotao">FILIPE FERNANDES</button>
        <button id="p14" class="botao" @click="carregueiNumBotao">JOANA LOPES</button>
        <button id="p15" class="botao" @click="carregueiNumBotao">RODRIGO TEIXEIRA</button>
      </div>
      <div class="tarefasTodas">
        <button id="r1" class="botao2" @click="carregueiNumBotao">ROLETA DA SORTE</button>
        <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
      </div>
    </div>
    <div v-show="segundaJanela">
      <div class="tarefasTodas">
        <h1>Ah! Rólêta dus Bólòs</h1>
        <img src="./assets/roulette.gif" />
        <button id="v1" class="botao" @click="carregueiNumBotao">VER RESULTADOS</button>
      </div>
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
export default {
  name: "app",
  data() {
    return {
      primeiraJanela: false,
      segundaJanela: true,
      terceiraJanela: false,
      participantes: [],
      tarefas: []
    };
  },
  methods: {
    carregueiNumBotao: function(event) {
      var _id = event.target.id;
      if (_id.includes("p")) this.botaoParticipante(_id);
      else if (_id.includes("t")) this.botaoTarefa(_id);
      else if (_id.includes("v")) this.botaoResultados(_id);
      else this.botaoRoleta();
    },
    botaoParticipante(id) {
      var index = this.participantes.indexOf(id);
      var botao = document.getElementById(id);
      if (index != -1) {
        this.participantes.splice(id, 1);
        botao.classList = "botao";
      } else {
        this.participantes.push(id);
        botao.classList = "botaoLigado";
      }
    },
    botaoTarefa(id) {
      var index = this.tarefas.indexOf(id);
      var botao = document.getElementById(id);
      if (index != -1) {
        this.tarefas.splice(id, 1);
        botao.classList = "botao";
      } else {
        this.tarefas.push(id);
        botao.classList = "botaoLigado";
      }
    },
    botaoResultados() {
      this.segundaJanela = false;
      this.terceiraJanela = true;
    },
    botaoRoleta() {
      this.primeiraJanela = false;
      this.segundaJanela = true;
      var that = this;
      setTimeout(function() {
        that.segundaJanela = false;
        that.terceiraJanela = true;
      }, 2000);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h3 {
  display: flex;
}

label {
  font-size: 10px;
}

.botao {
  margin: 5px;
}

.botaoLigado {
  margin: 5px;
  background: grey;
  color: white;
}

.botao2 {
  margin: 15px;
  background: teal;
  color: white;
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
</style>
