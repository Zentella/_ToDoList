<template>
  <div class="container">
    <div class="tarea">
      Tarea
      <input type="text" v-model="texto" placeholder="ingresa nueva tarea" />
      <button @click="guardar">Añade</button>
    </div>

    <div class="listaOk" v-if="listaOk">
      <ul>
        <li v-for="(item, index) in lista" :key="index">
          <span>{{ index }}: {{ item }}</span>
          <button @click="lista.splice(index, 1)">eliminar</button>
          <!--$emit se puede enviar directo desde el boton-->
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloVue",
  data() {
    return {
      listaOk: true,
      lista: [],
      tiempo: "",
      texto: "",
      eliminado: 0,
    };
  },
  methods: {
    guardar: function () {
      if (this.texto != "" && this.texto.trim().length != 0) { // para no guardar vacío
      // La función TRIM elimina todos los espacios en blanco o caracteres de espacio, excepto los espacios en blanco simples entre palabras en un valor de celda.
        this.lista.push(this.texto);
        this.texto = "";
        this.listaOk = "!this.listaOk";
      }
    },
  },
};
</script>

<style scoped>

.hellovue {
  color: gray;
  font-weight: bold;
  font-size: 50px;

}

.tarea {
  color: black;
  font-weight: bold;
  font-size: 20px;
  margin-top: 20px;
  margin-left: 50px;
  color: blue;

}

.lista {
  color: gray;
  font-weight: bold;
  font-size: 50px;
  margin-left: 100px;

}

.listaOk {
  color: black;
  font-weight: bold;
  margin-left: 100px;

}

button {
  border-radius: 12%;
}
</style>
