<script lang="ts">
import BarraNavegacao from './components/BarraNavegacao.vue'
import Produtos from './components/Produtos.vue'
import Personalizado from './components/Personalizado.vue'

export default {
  components: {
    BarraNavegacao,
    Produtos,
    Personalizado
  },
  data: () => ({
    tab: 1,
  }),
  methods: {
    mudarJanela(tab: number) {
      this.tab = tab;
    }
  },
  mounted() {
    this.mudarJanela(0);
  },
}
</script>

<template>
  <v-app>
    <BarraNavegacao @clicou-tab="(mudarJanela)"></BarraNavegacao>
    <v-window id="window" v-model="tab">
      <v-window-item value="0" key="0">
        <Produtos></Produtos>
      </v-window-item>
      <v-window-item value="1" key="1">
        <Personalizado></Personalizado>
      </v-window-item>
    </v-window>
  </v-app>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Montserrat");
.application {
  font-family: "Montserrat";
}
  #logo {
    margin-left: 35px;
  }
  #barra {
    padding: 0 10px;
  }
  #window {
    margin-top: 65px;
  }
</style>