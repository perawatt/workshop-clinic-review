<template>
  <div class="gif-list-container">
    <!-- Tabs -->
    <div class="tabs-container">
      <button
        class="tab-button"
        :class="{ active: activeTab === 'orders' }"
        @click="activeTab = 'orders'"
      >
        My Videos
      </button>
      <button
        class="tab-button"
        :class="{ active: activeTab === 'favorites' }"
        @click="onClickconfirm"
      >
        My Orders
      </button>
    </div>

    <!-- GIF List -->
    <div class="gif-list">
      <div class="gif-card" v-for="gif in displayedGifs" :key="gif.id">
        <img :src="gif.url" :alt="gif.title" class="gif-preview" />
        <p class="gif-title">{{ gif.title }}</p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

interface Gif {
  id: number;
  url: string;
  title: string;
}
const onClickconfirm = () => {
    navigateTo('userMyOrder')
  };

const activeTab = ref<'orders' | 'favorites'>('orders'); // Default tab

const ordersGifs = ref<Gif[]>([
  {
    id: 1,
    url: 'https://www.adorama.com/alc/wp-content/uploads/2021/05/bird-wings-flying-feature.gif',
    title: 'Bird Flying',
  },
  {
    id: 2,
    url: 'https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif',
    title: 'Funny Cat',
  },
  {
    id: 3,
    url: 'https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif',
    title: 'Dancing Banana',
  },
]);

const favoritesGifs = ref<Gif[]>([
  {
    id: 4,
    url: 'https://media.giphy.com/media/3o7abKhOpu0NwenH3O/giphy.gif',
    title: 'Simple Wave',
  },
  {
    id: 5,
    url: 'https://media.giphy.com/media/xT9IgzoKnwFNmISR8I/giphy.gif',
    title: 'Spinning Circle',
  },
  {
    id: 6,
    url: 'https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif',
    title: 'Smiling Emoji',
  },
]);

const displayedGifs = computed(() => {
  return activeTab.value === 'orders' ? ordersGifs.value : favoritesGifs.value;
});
</script>

<style scoped>
.gif-list-container {
  font-family: 'Arial', sans-serif;
  background-color: #f5f6fa;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* Tabs */
.tabs-container {
  display: flex;
  justify-content: space-around;
  background-color: white;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  padding: 10px 0;
}

.tab-button {
  flex: 1;
  padding: 10px 0;
  font-size: 16px;
  font-weight: bold;
  text-align: center;
  background-color: transparent;
  border: none;
  cursor: pointer;
  border-bottom: 2px solid transparent;
  transition: border-color 0.3s ease-in-out;
}

.tab-button.active {
  border-bottom: 2px solid #3498db;
  color: #3498db;
}

.tab-button:hover {
  background-color: #f0f0f0;
}

/* GIF List */
.gif-list {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
  justify-content: center;
  padding: 15px;
}

.gif-card {
  background: white;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  text-align: center;
  max-width: 200px;
  width: 100%;
}

.gif-preview {
  display: block;
  width: 100%;
  height: auto;
}

.gif-title {
  padding: 10px;
  font-size: 14px;
  font-weight: bold;
  color: #2c3e50;
}
</style>
