<template>
    <v-layout
        id="layout"
        style="padding: 5vh"
    >
        <CardProduto v-for="item in produtos"
            :key="item.id"
            :produto="item.produto"
            :preco="item.preco"
            :imagem="item.imagem"
        ></CardProduto>
    </v-layout>
</template>

<script setup>
import CardProduto from './CardProduto.vue';
import { ref } from 'vue'

const components = {CardProduto};
const produtos = ref([
  { 
    id: 1,
    produto: 'Brinco peixe',
    preco: 15,
    imagem: 'https://raw.githubusercontent.com/AirtonBorges/loja-brincos/main/loja-brincos/src/assets/imagem-peixe.jpg'
  },
  { 
    id: 2,
    produto: 'Brinco pirulito',
    preco: 20,
    imagem: 'https://raw.githubusercontent.com/AirtonBorges/loja-brincos/main/loja-brincos/src/assets/imagem-pirulito.jpg'
  },
  { 
    id: 3,
    produto: 'Brinco tanjiro',
    preco: 15,
    imagem: 'https://raw.githubusercontent.com/AirtonBorges/loja-brincos/main/loja-brincos/src/assets/imagem-tanjiro.jpg'
  },
  { 
    id: 3,
    produto: 'Brinco pato',
    preco: 16,
    imagem: 'https://raw.githubusercontent.com/AirtonBorges/loja-brincos/main/loja-brincos/src/assets/imagem-pato.jpg'
  }
])
</script>

<style scoped>
    #layout {
        display: grid;
        gap: 1rem;
        justify-items: center;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr))
    }
</style>