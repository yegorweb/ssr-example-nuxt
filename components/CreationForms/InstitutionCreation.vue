<!-- Форма создания учреждения -->
<template>
  <v-select label="Какое?" :items="institution_types" variant="underlined" />
  <v-text-field
    label="Название учреждения"
    placeholder="Детский садик 'Лопушок'"
    variant="underlined"
  ></v-text-field>
  <div class="w-100 d-flex justify-center ma-4">
    <v-btn to="/mainForm" color="accent">Создать</v-btn>
  </div>
</template>

<script setup>
let institution_types = [
  "Детский сад",
  "Курсы для дошкольников",
  "Средне-образовательная школа",
  "Гимназия",
  "Лицей",
];
</script>