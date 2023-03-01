<script setup>
import { ref } from "vue";
import topics from '../../fakeDB/topics'

let title = ref('')
let subtitle = ref('')
let text = ref('')
</script>

<template>
  <v-text-field v-model="title" label="Название" variant="underlined"></v-text-field>
  <v-text-field v-model="subtitle" label="Подзаголовок" variant="underlined"></v-text-field>
  <v-textarea v-model="text" auto-grow label="Текст" variant="underlined"></v-textarea>
  <v-select
    variant="underlined"
    label="Тема"
    :items="topics"
  />
  <v-file-input
    multiple
    accept="image/png, image/jpeg, image/bmp"
    label="Вы можете прикрепить фото"
    prepend-icon="mdi-camera"
    variant="underlined"
  ></v-file-input>
  <div class="w-100 d-flex justify-center ma-4">
    <v-btn to="/mainForm" color="accent">Создать</v-btn>
  </div>
</template>
