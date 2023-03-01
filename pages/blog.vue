<script setup>
import Post from "../components/Post.vue";
import BackButton from "../components/BackButton.vue";
import posts from "../fakeDB/posts";
</script>

<template>
  <v-container>
    <BackButton text="назад" />
    <v-row>
			<v-col v-for="post in posts" :key="post" cols="12" sm="6" md="4">
				<Post 
					:post="post"
				/>
      </v-col>
    </v-row>
  </v-container>
</template>

<style lang="scss" scoped>
</style>