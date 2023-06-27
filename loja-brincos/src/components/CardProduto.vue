<template>
  <v-card
    class="d-flex flex-column align-center justify-start"
    style="border: 2px solid #C62828;"
    max-width="370"
    width="100%"
    height="420"
  >
    <v-img
      style="padding-top: 10px;"
      width="95%"
      height="75%"
      cover
      aspect-ratio="16/9"
      :src="imagem"
    >
    </v-img>
    <v-card-title
        style="width: 100%;"
        class="d-flex justify-space-between">
            <span>{{produto}}</span><span>R${{preco}}</span>
    </v-card-title>
    <v-card-actions>
        <v-btn
            color="red-darken-3"
            block
            rounded="lg"
            width="100%"
          >
            Tenho interesse
          </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script setup>
    const props = defineProps({
        imagem: { type: String, required: true },
        produto: { type: String, required: true },
        preco: { type: Number, required: true },
    })
</script>

<style scoped>
    .fb-btn {
        border-color: thin solid red !important;
    }
</style>