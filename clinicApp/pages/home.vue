<template>
  <div class="gif-full-scroll-container">
    <!-- Search Bar -->
    <div class="search-bar">
      <input type="text" placeholder="Search for GIFs..." class="search-input" v-model="searchQuery" />
    </div>

    <!-- Full-Page Scrollable GIFs -->
    <div class="gif-list">
      <div class="gif-card" v-for="gif in filteredGifs" :key="gif.id">
        <div class="gif-full-view">
          <img :src="gif.url" :alt="gif.title" class="gif-preview" />
          <div class="gif-title">{{ gif.title }}</div>
          <button class="submit-btn" @click="onClickconfirm">จองคลินิค</button>
        </div>
      </div>
    </div>

    <!-- Bottom Action Buttons -->
    <div class="bottom-nav">
      <button class="nav-button">Home</button>
      <button class="nav-button" @click="onClickUploadVideo">+</button>
      <button class="nav-button" @click="onClickUserProfile">Profile</button>
    </div>
  </div>
</template>

<script lang="ts" setup>
const data = ref({
  searchQuery: "",
  gifs: [
    { id: 1, url: "https://www.adorama.com/alc/wp-content/uploads/2021/05/bird-wings-flying-feature.gif", title: "Bird Flying" },
    { id: 2, url: "https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif", title: "Funny Cat" },
    { id: 3, url: "https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif", title: "Dancing Banana" },
    { id: 4, url: "https://media.giphy.com/media/3o7abKhOpu0NwenH3O/giphy.gif", title: "Simple Wave" },
    { id: 5, url: "https://media.giphy.com/media/xT9IgzoKnwFNmISR8I/giphy.gif", title: "Spinning Circle" },
    { id: 6, url: "https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif", title: "Smiling Emoji" },
    { id: 7, url: "https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif", title: "Bouncing Ball" },
    { id: 8, url: "https://media.giphy.com/media/l0HUpt2s9Pclgt9Vm/giphy.gif", title: "Heartbeat" },
    { id: 9, url: "https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif", title: "Rotating Cube" },
    { id: 10, url: "https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif", title: "Loading Dots" },
  ],
});
const filteredGifs = computed(() => {
  if (!data.value.searchQuery) {
    return data.value.gifs;
  }
  return data.value.gifs.filter((gif) =>
    gif.title.toLowerCase().includes(data.value.searchQuery.toLowerCase())
  );
});

const onClickconfirm = () => {
  navigateTo('clinicCourse')
};

const onClickUploadVideo = () => {
  navigateTo('uploadVideo')
};

const onClickUserProfile = () => {
  navigateTo('userProfile')
};

</script>

<style scoped>
.gif-full-scroll-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
  font-family: 'Arial', sans-serif;
  background-color: black;
  overflow: hidden;
}

/* Search Bar */
.search-bar {
  position: sticky;
  top: 0;
  z-index: 2;
  padding: 10px;
  background-color: white;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.search-input {
  width: 100%;
  padding: 10px;
  border: 1px solid #dcdcdc;
  border-radius: 4px;
  font-size: 16px;
}

/* Full-Page GIF List */
.gif-list {
  flex-grow: 1;
  overflow-y: auto;
}

.gif-card {
  display: flex;
  flex-direction: column;
  height: 100vh;
  /* Full page for each GIF */
}

.gif-full-view {
  position: relative;
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: black;
}

.gif-preview {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.gif-title {
  position: absolute;
  bottom: 20px;
  left: 20px;
  color: white;
  background: rgba(0, 0, 0, 0.6);
  padding: 10px 15px;
  font-size: 18px;
  font-weight: bold;
  border-radius: 4px;
  z-index: 2;
}

/* Bottom Navigation */
.bottom-nav {
  position: fixed;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  justify-content: space-between;
  width: 90%;
  max-width: 600px;
  z-index: 3;
}

.nav-button {
  flex-grow: 1;
  margin: 0 5px;
  padding: 10px;
  background-color: #3498db;
  color: white;
  font-size: 16px;
  font-weight: bold;
  text-align: center;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: 0.3s ease-in-out;
}

.nav-button:hover {
  background-color: #2980b9;
}
</style>