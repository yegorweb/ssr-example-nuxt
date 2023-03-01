<script setup>
import phoneinput from "../../plugins/phoneinput";
import { ref } from "vue";

phoneinput.init_phone_input_mask();

let shop_types = ["Игрушки", "Канцтовары", "Спорттовары", "Книги"];
let social_networks = ref([]);
let legal = ref("");
</script>

<template>
  <v-row>
    <v-col  lg="6">
      <v-text-field variant="underlined" label="Название"></v-text-field>
    </v-col>
    <v-col lg="6">
      <v-text-field variant="underlined" label="Адрес"></v-text-field>
    </v-col>
  </v-row>
  <v-row>
    <v-col lg="6">
      <v-file-input
        variant="underlined"
        multiple
        accept="image/png, image/jpeg, image/bmp"
        label="Фотографии"
        prepend-icon="mdi-camera"
      ></v-file-input>
    </v-col>
    <v-col lg="6">
      <v-text-field
        variant="underlined"
        id="tel-input"
        label="Телефон"
      ></v-text-field>
    </v-col>
  </v-row>
  <v-row>
    <v-col lg="6">
      <v-select variant="underlined" label="Профиль" :items="shop_types" />
      <v-radio-group v-model="legal">
        <template v-slot:label>
          <div>Кто вы?</div>
        </template>

        <v-radio label="ИП" value="ie"></v-radio>
        <v-radio label="Юр. лицо" value="entity"></v-radio>
      </v-radio-group>
    </v-col>
    <v-col lg="6">
      <v-textarea variant="underlined" label="Описание магазина"></v-textarea>
    </v-col>
  </v-row>
  <v-row>
    <v-col lg="6">
      <!-- <v-text-field variant="underlined" 
            v-for="social_network, index in social_networks" 
            :key="index"
            v-model="social_networks[index]"
            label="Вставьте ссылку на соцсеть"
            append-inner-icon="mdi-clear"
            @click:append-inner="social_networks = social_networks.slice(index, index)"
            placeholder="instagram.com/vasiliy_pupkin.228"
          /> -->
    </v-col>
    <v-col lg="6"> </v-col>
  </v-row>
  <div class="w-100 d-flex justify-center ma-4">
    <v-btn to="/mainForm" color="accent">Создать</v-btn>
  </div>
</template>

