<template>
  <div class="gif-list-container">
    <!-- Search Bar -->
    <div class="search-bar">
      <input
        type="text"
        placeholder="Search for GIFs..."
        v-model="searchQuery"
        class="search-input"
      />
    </div>
  
    <!-- GIF Grid -->
    <div class="gif-grid">
      <div
        class="gif-card"
        v-for="gif in filteredGifs"
        :key="gif.id"
      >
        <img :src="gif.url" :alt="gif.title" class="gif-preview" />
        <div class="gif-title-overlay">
          <p>{{ gif.title }}</p>
        </div>
      </div>
    </div>
  </div>
  </template>
  
  <script>
  export default {
  name: "GifListPage",
  data() {
    return {
      searchQuery: "",
      gifs: [
        {
          id: 1,
          url: "https://www.adorama.com/alc/wp-content/uploads/2021/05/bird-wings-flying-feature.gif",
          title: "Bird Flying",
        },
        {
          id: 2,
          url: "https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif",
          title: "Funny Cat",
        },
        {
          id: 3,
          url: "https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif",
          title: "Dancing Banana",
        },
        {
          id: 4,
          url: "https://media.giphy.com/media/3o7abKhOpu0NwenH3O/giphy.gif",
          title: "Simple Wave",
        },
        {
          id: 5,
          url: "https://media.giphy.com/media/xT9IgzoKnwFNmISR8I/giphy.gif",
          title: "Spinning Circle",
        },
        {
          id: 6,
          url: "https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif",
          title: "Smiling Emoji",
        },
        {
          id: 7,
          url: "https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif",
          title: "Bouncing Ball",
        },
        {
          id: 8,
          url: "https://media.giphy.com/media/l0HUpt2s9Pclgt9Vm/giphy.gif",
          title: "Heartbeat",
        },
        {
          id: 9,
          url: "https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif",
          title: "Rotating Cube",
        },
        {
          id: 10,
          url: "https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif",
          title: "Loading Dots",
        },
      ],
    };
  },
  computed: {
    filteredGifs() {
      if (!this.searchQuery) {
        return this.gifs;
      }
      return this.gifs.filter((gif) =>
        gif.title.toLowerCase().includes(this.searchQuery.toLowerCase())
      );
    },
  },
  };
  </script>
  
  <style scoped>
  .gif-list-container {
  padding: 20px;
  font-family: 'Arial', sans-serif;
  background-color: #f5f6fa;
  min-height: 100vh;
  }
  
  .search-bar {
  margin-bottom: 20px;
  text-align: center;
  }
  
  .search-input {
  width: 80%;
  padding: 10px;
  font-size: 16px;
  border: 1px solid #dcdcdc;
  border-radius: 4px;
  }
  
  .gif-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 15px;
  }
  
  .gif-card {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  }
  
  .gif-preview {
  display: block;
  width: 100%;
  height: auto;
  }
  
  .gif-title-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  background: rgba(0, 0, 0, 0.5);
  color: white;
  text-align: center;
  padding: 5px 0;
  font-size: 14px;
  font-weight: bold;
  }
  </style>
  