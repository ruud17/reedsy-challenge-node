<script setup lang="ts">
import type { Book } from '@/types/book';
import { type PropType } from 'vue';

defineProps({
  book: {
    type: Object as PropType<Book>,
    required: true
  }
});
</script>

<template>
  <v-expansion-panel-title :hide-actions="true">
    <v-row>
      <v-col cols="6" class="font-weight-bold">
        <div class="d-flex">
          <v-img
            cols="4"
            class="bg-white"
            max-width="80"
            max-height="100"
            width="80"
            height="100"
            :src="book.cover_image"
            cover
          ></v-img>
          <div class="d-flex flex-column pl-4">
            <p class="text-h7 font-weight-bold pb-2">{{ book.title }}</p>
            <p class="text-h7 font-weight-medium text-disabled">{{ book.author }}</p>
          </div>
        </div>
      </v-col>
      <v-col cols="2" class="d-flex font-weight-bold align-center text-h7 justify-center">
        <span> {{ book.releaseDate }}</span>
      </v-col>
      <v-col cols="2" class="d-flex font-weight-bold align-center text-h7 justify-center">
        <span> {{ book.rating }}/10</span>
      </v-col>
      <v-col cols="2" class="d-flex flex-column align-center justify-center">
        <ul v-for="s in book.buyOn" :key="s">
          <li class="font-weight-bold text-h7">{{ s }}</li>
        </ul>
      </v-col>
    </v-row>
  </v-expansion-panel-title>
</template>

<style scoped>
ul {
  list-style-type: none;
}

ul li {
  color: rgb(164, 206, 96);
}
</style>
