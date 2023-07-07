<template>
  <div class="general">
    <div id="app">
      <transition name="fade" appear>
        <div class="modal-overlay" v-if="showModal" @click="showModal = false"></div>
      </transition>
      <transition name="pop" appear>
        <div class="modal" role="dialog" v-if="showModal">
          <h1>Bienvenid@ a mi primer VUE SPA</h1>
          <p>Nunca olvide leer el README ni tomar jugo de manzana</p>
          <button @click="showModal = false" class="button">🧃</button>
        </div>
      </transition>
    </div>
    <div class="container">
      <label for="id">ID:</label>
      <input type="number" class="input" v-model.number="id" min="1" max="100" :disabled="posts.length === 0">
      <br>
      <label for="title">Título:</label>
      <input type="text" v-model="title" class="title-text" readonly>
      <br>
      <div class="text-container">
        <label for="text" class="label">Texto:</label>
        <div id="text" class="text-content">
          {{ text }}
        </div>
        <div class="button-container">
          <button class="button-rightleft" @click="previous" :disabled="id <= 1 || posts.length === 0">&lt;</button>
          <button class="button-rightleft" @click="next" :disabled="id >= 100 || posts.length === 0">&gt;</button>
        </div>
      </div>
      <br>
      <label for="counter">Contador:</label>
      <input type="number" v-model="counter" readonly>
      <br>
      <button class="comic-button" @click="loadData">Cargar</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      id: 0,
      title: '',
      text: '',
      counter: 0,
      posts: [],
      showModal: true
    };
  },
  methods: {
    loadData() {
      axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(response => {
          this.posts = response.data;
          this.id = 1;
          this.counter++;
          this.updateData();
        })
        .catch(error => {
          console.error(error);
        });
    },
    next() {
      if (this.id < 100) {
        this.id++;
        this.updateData();
      }
    },
    previous() {
      if (this.id > 1) {
        this.id--;
        this.updateData();
      }
    },
    updateData() {
      const post = this.posts.find(p => p.id === this.id);
      if (post) {
        this.title = post.title;
        this.text = post.body;
      }
    }
  },
  watch: {
    id(newValue) {
      if (newValue === "") {
        this.title = "";
        this.text = "";
      } else if (newValue < 1) {
        this.id = 1;
      } else if (newValue > 100) {
        this.id = 100;
      } else {
        this.updateData();
      }
    }
  }

};
</script>
