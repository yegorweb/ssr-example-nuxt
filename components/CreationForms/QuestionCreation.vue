<script setup>
import topics from '../../fakeDB/topics'
import { ref } from 'vue'

let question = ref('')
let answer = ref('')

let know_answer = ref(false)
</script>

<template>
  <v-select 
    :items="topics" 
    label="Тема" 
    chips 
    multiple 
    variant="underlined"
  />

  <v-text-field 
    v-model="question" 
    label="Вопрос" 
    variant="underlined"
  />

  <v-checkbox 
    v-model="know_answer"
    label="Знаю ответ"
  />
  <Transition name="bounce">
    <v-text-field 
      v-if="know_answer"
      v-model="answer"
      label="Ответ"
      variant="underlined"
    />    
  </Transition>

  <!-- FUTURE: надо это убрать в MainForm, т. к. не соответсвует принципу DRY -->
  <div class="w-100 d-flex justify-center ma-4">
    <v-btn to="/mainForm" color="accent">Создать</v-btn>
  </div>
</template>