<template>
  <div id="app">
    <h3>{{ titulo }}</h3>
    <div class="form">
      <div class="form-group">
        <label>Titulo</label>
        <input class="form-control" type="text" v-model="nota.titulo" />
      </div>
      <div class="form-group">
        <label>Texto</label>
        <textarea class="form-control" v-model="nota.texto"></textarea>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      titulo: "Gestion de notas",
      nota: {
        titulo: "",
        texto: ""
      },
      notas: [
        {
          titulo: "Ir al cine",
          texto: "Examinar las peliculas",
          fecha: new Date(Date.now()).toLocaleDateString()
        }
      ]
    };
  },
  methods: {
    agregarNota: function() {
      let { texto, titulo } = this.nota;
      this.notas.push({
        titulo,
        texto,
        fecha: new Date(Date.now()).toLocaleDateString()
      });
    }
  }
};
</script>

<style>
.form {
  text-align: left;
}
</style>
