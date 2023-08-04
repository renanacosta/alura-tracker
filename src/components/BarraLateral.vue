<template>
  <header>
    <h1 class="image">
      <img src="../assets/logo.png" alt="Logo" />
    </h1>
    <button class="button" @click="alterarTema">
      {{ textoBotao }}
    </button>
    <p class="author">By Renan Acosta</p>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BarraLateral",
  emits: ["aoTemaAlterado"],
  data() {
    return {
      modoEscuroAtivo: false,
    };
  },
  computed: {
    textoBotao() {
      if (this.modoEscuroAtivo) {
        return "Desativar modo escuro";
      } else {
        return "Ativar modo escuro";
    }
    },
  },
  methods: {
    alterarTema() {
      this.modoEscuroAtivo = !this.modoEscuroAtivo;
      this.$emit("aoTemaAlterado", this.modoEscuroAtivo);
    },
  },
});
</script>

<style scoped>
.image {
margin-bottom: 1rem;
}

.button {
  background: #fcba03;
  color: #5c5a5a;
  font-weight: bold;
  border: none;
  margin-bottom: 1rem;
}

header {
  padding: 1rem;
  background: #222;
  width: 100%;
  height: 100vh;
  text-align: center;
}
.author {
  color: #fff;
  font-size: 1rem;
  margin-top: 1rem;
  border: 1px solid #fff;
  border-radius: 5px;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
