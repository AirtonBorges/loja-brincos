<script lang="ts">
export default {
  data: () => ({
    tab: null,
    colapsarBarra: false,
  }),
  methods: {
    onResize(){
      this.colapsarBarra = window.innerWidth < 768;
      console.log(this.colapsarBarra)
    }
  },
}
</script>

<template>
  <v-app>
    <v-app-bar
      v-resize="onResize"
      flat
      color="red-darken-3"
      class="d-flex justify-space-between"
    >
      <img id="logo"
        width="150"
        src="./assets/LOJA_BRANCA_HORIZ.webp"
      />
      <v-spacer></v-spacer>
      <v-expand-transition>
        <v-tabs
          v-if="!colapsarBarra"
          v-model="tab"
        >
          <v-tab>Brincos</v-tab>
          <v-tab>Pulseiras</v-tab>
          <v-tab>Personalização</v-tab>
        </v-tabs>
      </v-expand-transition>
      <v-expand-transition>
        <v-app-bar-nav-icon
          icon="mdi-dots-vertical"
          v-if="colapsarBarra"
        >
          ...
        </v-app-bar-nav-icon>
      </v-expand-transition>
    </v-app-bar>
    <v-window v-model="tab">
      <v-window-item v-for="n in 3" :key="n" :value="n">
        <v-container fluid>
          <v-row>
            <v-col v-for="i in 6" :key="i" cols="12" md="4">
              <v-img
                :src="`https://picsum.photos/500/300?image=${i * n * 5 + 10}`"
                :lazy-src="`https://picsum.photos/10/6?image=${i * n * 5 + 10}`"
                aspect-ratio="1"
              ></v-img>
            </v-col>
          </v-row>
        </v-container>
      </v-window-item>
    </v-window>
  </v-app>
</template>

<style scoped>
  #logo {
    margin-left: 50px;
  }

</style>