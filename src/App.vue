<template>
  <div id="app">
    <h1>Ah! Rólêta dus Bólòs</h1>
    <h3>ESCOLHE AS TAREFAS:</h3>
    <div class="tarefasTodas">
      <button class="botao">IR ÀS COMPRAS</button>
      <button class="botao">PREPARAR A REFEIÇÃO</button>
      <button class="botao">PÔR A MESA</button>
      <button class="botao">LEVANTAR A MESA</button>
      <button class="botao">LAVAR A LOIÇA</button>
      <div class="tarefasOpcionais">
        <button class="botao tarefaOpcionalBotao">VARRER O CHÃO</button>
        <button class="botao tarefaOpcionalBotao">SECAR A LOIÇA</button>
        <button class="botao tarefaOpcionalBotao">LEVAR O LIXO</button>
      </div>
    </div>
    <h3>ESCOLHE OS BOLOS:</h3>
    <div class="tarefasTodas">
      <button class="botao">CARMEN MARTINS</button>
      <button class="botao">PEDRO OLIVEIRA</button>
      <button class="botao">PATRÍCIA NEVES</button>
      <button class="botao">PEDRO SARDINHA</button>
      <button class="botao">MIGUEL CASTELA</button>
      <button class="botao">RAFAELA ROSA</button>
      <button class="botao">SOFIA COTRIM SANTOS</button>
      <button class="botao">JOSÉ MIGUEL POMBO</button>
      <button class="botao">RUI COTRIM SANTOS</button>
      <button class="botao">CATARINA SANTOS</button>
      <button class="botao">ALESSANDRO GUZZO</button>
      <button class="botao">TERESA GUIOMAR</button>
      <button class="botao">FILIPE FERNANDES</button>
      <button class="botao">JOANA LOPES</button>
    </div>
    <div class="tarefasTodas">
      <button class="botao2">ROLETA DA SORTE</button>
      <label>Todos os direitos reservados @ Carmen Martins & Pedro Oliveira . 2020</label>
    </div>
  </div>
</template>

<script>
export default {
  name: "app"
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

label{
  font-size: 10px
}

.botao {
  margin: 5px;
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
