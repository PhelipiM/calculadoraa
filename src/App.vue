<script>
export default {
 data(){
  return {
    valorConta: 0,
    Gorjeta: 20,
    Pessoas: 1,
  };
 },
 methods: {
  calcular(){
    const valorConta = this.valorConta;
    const Gorjeta = this.Gorjeta;
    const Pessoas = this.Pessoas;
    let valorGorjeta = 0;
    let valorTotal= {};

    valorGorjeta = valorConta * (Gorjeta / 100);
    valorTotal = (valorConta + valorGorjeta) / Pessoas;

    valorTotal = Math.round(valorTotal * 100) / 100;
    valorTotal = valorTotal.toFixed(2);

    console.log(valorTotal);

    document.getElementById("resultado").innerHTML = valorTotal;

  }
 }
};


</script>

<template>

  <div class="main">

    <h3>Calculadora</h3>

    <form>

      <label>
        <p>Preço do jantar</p>
        <input type="number" v-model="valorConta" id="valorConta">
      </label>

      <label>
        <p>Gorjeta  </p>
        <select v-model="Gorjeta" id="valorGorjeta">
          <option value="30">30% Ótimo serviço</option>
          <option value="25">25% Muito bom</option>
          <option value="20">20% Bom</option>
          <option value="15">15% Aceitável</option>
          <option value="10">10% Ruim</option>
          <option value="5">5% "Eca"</option>
        </select>
      </label>

      <label>
        <p>Pessoas que vão dividir a conta</p>
        <input v-model="Pessoas" type="number" id="Pessoas">
      </label>

      <label>
        <p>Calcular:</p>
        <button type="button" @click="calcular">R$:<span id="resultado">0,00</span></button>
      </label>

    </form>

  </div>

</template>

<style scoped>
  
  .main {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    padding: 25px;
    border:solid;
    border-radius: 20px;
     background-color: #e9e9e9 ;
    
  }

  h3 {
    font-size: 50px;
  }

  input, select {
    margin-bottom: 30px;
  }

  input, select, button {
    width: 250px;
    height: 25px;
    font-size: 18px;
    border: 1px black solid;
    border-radius: 2px;
    text-align: center;
    transition: 0.25s;
    cursor: pointer;
  }

  button {
    background-color: #32a838;
    height: 50px;
    font-size: 24px;
    margin-bottom: 10px;
  }

  button:hover {
    background-color: #29802d;
  }

</style>