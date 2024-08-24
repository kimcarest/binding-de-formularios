<template>
  <div id="app">
    <form>
      <p class="instrucciones">Coloca los datos de tu propia tarjeta de crédito</p>
      <div>
        <label>Título de la tarjeta: </label>
        <input v-model="tituloTarjeta" placeholder="Visa Classic Credito"/>
      </div>

      <div>
        <label>Chip SRC: </label>
        <input v-model="chipSRC" placeholder="/chip.png"/>
      </div>

      <div>
        <label>Número: </label>
        <input v-model="numero" placeholder="400 500 600 700"/>
      </div>

      <div>
        <label>Fecha de expiración: </label>
        <input v-model="fechaExp" placeholder="01/30"/>
      </div>

      <div>
        <label>Propietario: </label>
        <input v-model="propietario" placeholder="William Henry Gates III"/>
      </div>

      <div>
        <label>Tipo de tarjeta SRC: </label>
        <input v-model="tarjetaSRC" placeholder="/visa.png"/>
      </div>
    </form>

    <div class="carnet">
      <h3>{{ tituloTarjeta }}</h3>
      <img width="40" :src="require(`@/assets${srcChip}`)" alt="" />
      <div>
        <h2>{{ numero }}</h2>
        <span>Fecha Exp: <b>{{ fechaExp }}</b></span>
      </div>
      <footer>
        <span>{{ propietario }}</span>
        <img :src="require(`@/assets${srcTarjeta}`)" width="60" />
      </footer>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      numero: '400 500 600 700',
      tituloTarjeta: 'Visa Classic Crédito',
      fechaExp: '01/30',
      propietario: 'William Henry Gates III',
      srcTarjeta: '/visa.png',
      srcChip: '/chip.png'
    }
  }
}
</script>

<style>
* {
  margin: 0;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60vh;
  font-size: 10px;
  font-family: sans-serif;
}

#app {
  display: flex;
  gap: 40px;
}

form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}

form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

.carnet {
  width: 400px;
  height: 230px;
  background: #1c1a1e;
  color: white;
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

b {
  font-size: 16px;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>