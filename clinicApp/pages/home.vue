<template>
  <div class="home-container">
    <!-- Search Bar -->
    <div class="search-bar">
      <input
        type="text"
        placeholder="Search..."
        class="search-input"
        v-model="searchQuery"
      />
    </div>

    <!-- GIF Cards -->
    <div
      class="gif-card"
      v-for="(gif, index) in filteredGifs"
      :key="gif.id"
      :style="{ transform: `translateY(${(index - activeIndex) * 100}%)` }"
    >
      <!-- GIF -->
      <img :src="gif.url" alt="GIF" class="gif" />

      <!-- GIF Info -->
      <div class="gif-info">
        <div class="title-container">
          <h2 class="title">
            {{ gif.title }}
          </h2>
          <button class="mini-button" @click="onClickClinicCourse(gif.id)">
            จองคลินิค
          </button>
        </div>
        <p class="description">{{ gif.description }}</p>
      </div>
    </div>

    <!-- Bottom Action Menu -->
    <div class="bottom-action-menu">
      <button class="action-button" @click="goHome">Home</button>
      <button class="action-button" @click="onClickUploadVideo">+</button>
      <button class="action-button" @click="onClickUserProfile">Profile</button>
    </div>

    <!-- Popup Message -->
    <div v-if="isPopupVisible" class="popup">
      <p>{{ popupMessage }}</p>
      <button class="close-button" @click="closePopup">Close</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: 0, // Current GIF index
      searchQuery: '', // Search input value
      isPopupVisible: false, // Controls the visibility of the popup
      popupMessage: '', // Message to display in the popup
      gifs: [
        {
          id: 1,
          url: 'https://media.giphy.com/media/3o7abKhOpu0NwenH3O/giphy.gif',
          title: 'Relaxing Spa Treatment',
          description:
            'A soothing GIF showcasing a relaxing spa treatment at a beauty clinic.',
        },
        {
          id: 2,
          url: 'https://media.giphy.com/media/xT9IgzoKnwFNmISR8I/giphy.gif',
          title: 'Facial Care',
          description: 'A GIF highlighting a rejuvenating facial care session.',
        },
        {
          id: 3,
          url: 'https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif',
          title: 'Skincare Routine',
          description:
            'A quick glimpse into a professional skincare routine at a beauty clinic.',
        },
        {
          id: 4,
          url: 'https://media.giphy.com/media/l0HUpt2s9Pclgt9Vm/giphy.gif',
          title: 'Massage Therapy',
          description:
            'A calming GIF of a massage therapy session for relaxation and wellness.',
        },
        {
          id: 5,
          url: 'https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif',
          title: 'Laser Treatment',
          description:
            'A demonstration of advanced laser treatment for skin care.',
        },
        {
          id: 6,
          url: 'https://media.giphy.com/media/3o7abKhOpu0NwenH3O/giphy.gif',
          title: 'Manicure Session',
          description:
            'A GIF showing a manicure session for nail care and beauty.',
        },
        {
          id: 7,
          url: 'https://media.giphy.com/media/xT9IgzoKnwFNmISR8I/giphy.gif',
          title: 'Hair Styling',
          description: 'A stylish GIF of hair styling at a beauty clinic.',
        },
        {
          id: 8,
          url: 'https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif',
          title: 'Makeup Application',
          description:
            'A professional makeup application session for a flawless look.',
        },
        {
          id: 9,
          url: 'https://media.giphy.com/media/l0HUpt2s9Pclgt9Vm/giphy.gif',
          title: 'Body Scrub',
          description:
            'A rejuvenating body scrub session for smooth and glowing skin.',
        },
        {
          id: 10,
          url: 'https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif',
          title: 'Hydration Therapy',
          description:
            'A GIF showcasing hydration therapy for refreshed and healthy skin.',
        },
      ],
    };
  },
  computed: {
    filteredGifs() {
      // Filter GIFs based on the search query
      return this.gifs.filter((gif) =>
        gif.title.toLowerCase().includes(this.searchQuery.toLowerCase())
      );
    },
  },
  methods: {
    handleScroll(event) {
      const direction = event.deltaY > 0 ? 1 : -1;
      const newIndex = this.activeIndex + direction;
      if (newIndex >= 0 && newIndex < this.filteredGifs.length) {
        this.activeIndex = newIndex;
      }
    },
    // Action for Home button (placeholder for now)
    goHome() {
      console.log('Navigating to Home...');
    },
    // Action for Favorites button
    onClickClinicCourse() {
      console.log('Navigating to Clinic Course...');
      navigateTo('clinicCourse');
    },
    // Action for Favorites button
    onClickUploadVideo() {
      console.log('Navigating to Upload Video...');
      navigateTo('uploadVideo');
    },
    // Action for Settings button
    onClickUserProfile() {
      console.log('Navigating to User Profile...');
      navigateTo('userProfile');
    },
  },
  mounted() {
    window.addEventListener('wheel', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('wheel', this.handleScroll);
  },
};
</script>

<style scoped>
/* Main Container */
.home-container {
  position: relative;
  height: 100vh;
  overflow: hidden;
  background-color: black;
}

/* Search Bar */
.search-bar {
  position: sticky;
  top: 0;
  z-index: 3;
  padding: 10px;
  background-color: white;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.search-input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 1px solid #dcdcdc;
  border-radius: 4px;
}

/* GIF Card */
.gif-card {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transition: transform 0.5s ease;
}

.gif {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.gif-info {
  position: absolute;
  bottom: 20px;
  left: 20px;
  color: white;
}

.title-container {
  display: flex;
  align-items: center;
}

.title {
  font-size: 24px;
  font-weight: bold;
  cursor: pointer;
  color: #3498db;
}

.title:hover {
  text-decoration: underline;
}

/* Mini Button */
.mini-button {
  margin-left: 10px;
  font-size: 14px;
  padding: 5px;
  background-color: #2c3e50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.mini-button:hover {
  background-color: #1a242f;
}

.description {
  font-size: 16px;
  margin-top: 5px;
}

/* Bottom Action Menu */
.bottom-action-menu {
  position: fixed;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  justify-content: space-around;
  width: 90%;
  max-width: 600px;
  background: rgba(0, 0, 0, 0.6);
  padding: 10px;
  border-radius: 8px;
  z-index: 2;
}

.action-button {
  flex: 1;
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
  transition: background-color 0.3s ease-in-out;
}

.action-button:hover {
  background-color: #2980b9;
}

/* Popup Message */
.popup {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  z-index: 10;
  text-align: center;
}

.popup p {
  margin: 0 0 10px;
  font-size: 16px;
  font-weight: bold;
  color: #2c3e50;
}

.close-button {
  padding: 10px 20px;
  font-size: 14px;
  background-color: #3498db;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}

.close-button:hover {
  background-color: #2980b9;
}
</style>
