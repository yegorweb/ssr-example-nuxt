<script setup>
import { ref } from "vue";
import topics from '../../fakeDB/topics'

let article = ref("");
</script>

<template>
  <v-text-field label="Название" variant="underlined"></v-text-field>
  <v-select chips label="Тема" :items="topics" multiple variant="underlined" />
  <QuillEditor
    v-model="article"
    placeholder="Текст"
    :toolbar="[
      [{ size: ['small', false, 'large', 'huge'] }],
      ['bold', 'italic', 'underline', 'strike'],
    ]"
  />

  <div class="w-100 d-flex justify-center ma-4">
    <v-btn to="/mainForm" color="accent">Создать</v-btn>
  </div>
</template>

