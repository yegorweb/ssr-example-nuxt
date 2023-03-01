<script setup>
const router = useRouter()

const routTo = (to) => {
  router.push({ path: to });
};
</script>

<template>
  <div class="home-page">
    <v-hover v-slot="{ isHovering, props }" open-delay="200">
      <v-card
        class="answer text-center"
        color="secondary"
        :elevation="isHovering ? 16 : 2"
        :class="{ 'on-hover': isHovering }"
        v-bind="props"
      >
        Ответы
      </v-card>
    </v-hover>
    <v-card class="blog" color="success" @click="routTo('/blog')">Блоги </v-card>
    <v-card class="photo_2" color="primary">
      <v-img height="100%" src="../assets/images/photo_2.jpeg" cover> </v-img
    ></v-card>
    <v-card class="photo_1" color="primary">
      <v-img height="100%" src="../assets/images/photo_1.jpg" cover> </v-img
    ></v-card>
    <v-card class="find" color="secondary">Найти</v-card>
    <v-card class="create" color="accent" @click="routTo('/mainForm')">
      Создать</v-card
    >
    <v-card class="advert" color="primary"> Объявления</v-card>
    <v-card class="dictionary" color="primary">Справочники </v-card>
    <v-card class="photo_3" color="success">
      <v-img height="100%" src="../assets/images/photo_3.jpg" cover> </v-img
    ></v-card>

    <v-card class="article" color="success"> Статьи</v-card>
  </div>
</template>



<style lang="scss" scoped>
.home-page {
  .v-card {
    text-transform: uppercase;
    display: flex;
    justify-content: center;
    align-items: center;
    .v-img {
      :hover {
        animation: bounce-scale 1s;
      }
    }
  }
}
@media (max-width: 960px) {
  .home-page {
    padding: 10px;
    display: grid;
    height: calc(100vh - 100px);
    gap: 5px 5px;
    grid-template-columns: 1fr 1fr 1fr 1f;
    grid-template-rows: 1fr 1fr 1fr 1fr 1fr 1fr;
    grid-template-areas:
      "photo_1 photo_1 answer answer "
      "photo_1 photo_1 blog blog"
      "find find photo_2 photo_2"
      "create create photo_2 photo_2"
      "photo_3 photo_3 dictionary dictionary"
      "advert advert article article";
  }
}
@media (min-width: 961px) {
  .home-page {
    padding: 10px;
    display: grid;
    height: calc(100vh - 100px);
    gap: 10px 10px;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr 1fr;
    grid-template-areas:
      "answer answer blog blog photo_2 photo_2"
      "photo_1 photo_1 find create photo_2 photo_2"
      "photo_1 photo_1 find create photo_2 photo_2"
      "dictionary dictionary photo_3 photo_3 advert article";
  }
}
.blog {
  grid-area: blog;
}
.answer {
  grid-area: answer;
}
.photo_1 {
  grid-area: photo_1;
}
.photo_2 {
  grid-area: photo_2;
}
.photo_3 {
  grid-area: photo_3;
}
.article {
  grid-area: article;
}
.find {
  grid-area: find;
}
.advert {
  grid-area: advert;
}

.dictionary {
  grid-area: dictionary;
}

.create {
  grid-area: create;
}
</style>
