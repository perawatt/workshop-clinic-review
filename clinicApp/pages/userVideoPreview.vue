<template>
  <div class="gif-view-container">
    <!-- Full GIF View -->
    <div class="gif-full-view">
      <img
        src="https://www.adorama.com/alc/wp-content/uploads/2021/05/bird-wings-flying-feature.gif"
        alt="Current GIF"
        class="gif-image"
      />
      <div class="gif-title">{{ title }}</div>

      <!-- "..." Button -->
      <div class="options-button-container">
        <button class="options-button" @click="toggleActionsMenu">...</button>
        <!-- Actions Menu -->
        <ul v-if="showActionsMenu" class="actions-menu">
          <li @click="performAction('edit')">Edit</li>
          <li @click="performAction('share')">Share</li>
          <li @click="performAction('delete')">Delete</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GifViewPage',
  data() {
    return {
      title: 'Bird Flying',
      showActionsMenu: false, // Track whether the actions menu is visible
    };
  },
  methods: {
    toggleActionsMenu() {
      this.showActionsMenu = !this.showActionsMenu; // Toggle menu visibility
    },
    performAction(action) {
      this.showActionsMenu = false; // Close the menu
      console.log(`Performing action: ${action}`);
      // Add logic for specific actions if needed
    },
  },
};
</script>

<style scoped>
.gif-view-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
  font-family: 'Arial', sans-serif;
  background-color: black;
}

/* Full GIF View */
.gif-full-view {
  position: relative;
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: black;
}

.gif-image {
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

/* "..." Button */
.options-button-container {
  position: absolute;
  bottom: 20px;
  right: 20px;
  z-index: 3;
}

.options-button {
  background-color: rgba(0, 0, 0, 0.6);
  color: white;
  font-size: 18px;
  font-weight: bold;
  border: none;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  cursor: pointer;
  text-align: center;
}

.options-button:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* Actions Menu */
.actions-menu {
  position: absolute;
  bottom: 70px;
  right: 20px;
  background: white;
  border: 1px solid #dcdcdc;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  list-style: none;
  padding: 10px 0;
  margin: 0;
  z-index: 4;
}

.actions-menu li {
  padding: 10px 20px;
  cursor: pointer;
  color: #2c3e50;
  font-size: 16px;
}

.actions-menu li:hover {
  background-color: #f0f0f0;
}
</style>
