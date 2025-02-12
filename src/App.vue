<script setup>
import { ref } from "vue";
const posts = ref([]);
const text = ref("hello");
function addPost() {
  posts.value.push(text.value);
  text.value = "";
}
</script>

<template>
  <main>
    <h1 id="titre" class="crevette">Bonjour</h1>
    <div class="container">
      <form class="card" @submit.prevent="addPost">
        <textarea name="post" id="post" placeholder="saissiez" v-model="text"></textarea>
        <button type="submit">Publier</button>
      </form>
      <p v-for="(post, index) in posts" :key="index">{{ post }}</p>
    </div>
  </main>
</template>
