<script>
export default{
  name: "App",
  data(){
    return{
      colordeFondo: "black",
      colordeTexto: "white",
      borde: "25",
      tipoDeFigura: "",
      contenidoTextual: "Awesome Vue.js",
      tamañoDeTexto: "",
      tipografia: "",
      textShow: true,
      tipografias: ["fantasy", "cursive", "monospace","times new roman", "serif","courier"],
      opaco: "",
    };
  },
};
</script>

<template>
  <div id="app">
    <form>
      <div>
        <label> Color de Fondo</label>
        <input type="text" v-model="colordeFondo">
      </div>

      <div>
        <label>Color de Texto</label>
        <input type="text" v-model="colordeTexto">
      </div>

      <div>
        <span>Mostrar Texto <input type="checkbox" v-model="textShow"></span>
      </div>

      <div>
        <label>Borde</label>
        <input type="range" min="0" max="150" v-model="borde">
      </div>

      <div>
        <label>Contenido textual</label>
        <textarea v-model="contenidoTextual"></textarea>
      </div>

      <div>
        <label>Tipografia</label>
        <select v-model="tipografia" >
        <option :value="tipografia" v-for="tipografia in tipografias">
          {{ tipografia }}
        </option>
      </select>
      </div>
       
      <div>
        <label>Opaco <input type="checkbox" v-model="opaco"></label>
      </div>

      <div>
        <label>Tamaño de letra</label>
        
      <div>
      <input type="radio" name="tamaño" value="16px" v-model="tamañoDeTexto">

      <label>Pequeño</label>
      <input type="radio" name="tamaño" value="25px" v-model="tamañoDeTexto">

       <label>Mediano</label>
       <input type="radio" name="tamaño" value="40px" v-model="tamañoDeTexto">

       <label>Grande</label>
      </div>
    </div>
    </form>
   
    <main>
      <div class="figura" :style="{
        background: colordeFondo,
        borderRadius: borde + '%',
        color: colordeTexto,
        fontFamily: tipografia,
        fontSize: tamañoDeTexto,
      }"
       :class="{opaco}"
      >
      <p v-show="textShow">{{ contenidoTextual }}</p>
      </div>
    </main>
  </div>
</template>

<style scoped>
body{
  margin: 0;
}

#app{
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  display: grid;
  grid-template-columns: 400px 1fr;
  height: 100vh;
}

main{
  display: flex;
  justify-content: center;
  align-items: center;
}

.figura{
  width: 30vw;
  height: 30vw;
  display: flex;
  align-items: center;
  justify-content: center;
}

form{
  background: darkslategray;
  color: white;
  display: flex;
  flex-direction: column;
  gap: 15px;
  padding: 40px;
  margin-right: 20px;
}

form > div {
  display: flex;
  flex-direction: column;
  text-align: left;
  
}

.opaco{
  opacity: 0.5;
}
</style>
