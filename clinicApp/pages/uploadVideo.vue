<template>
  <div class="upload-container">
    <div class="upload-card">

      <div class="video-upload">
        <h2>Upload a Video</h2>
        <input type="file"  accept="video/*" />

       

        <!-- <div v-if="videoFile">
          <h3>Video Preview:</h3>
          <video v-if="videoFile" width="320" height="240" controls>
            <source :src="videoPreviewUrl" type="video/mp4" />
            Your browser does not support the video tag.
          </video>
        </div> -->
      </div>
      <div  @click="onClickconfirmVedio">
        <button  class="submit-btn">next</button>
      </div>
    </div>
  </div>

</template>

<script setup lang="ts">
const onClickconfirmVedio = () => {
  navigateTo('uploadVideoConfirm')
};

</script>

<style scoped>
 .upload-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f5f6fa;
  font-family: 'Arial', sans-serif;
  }
  
  .upload-card {
  background: white;
  border-radius: 8px;
  padding: 20px 30px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  max-width: 500px;
  width: 100%;
  }

.video-upload {
  text-align: center;
  margin-top: 20px;
  height: 20vh;

}

video {
  margin-top: 20px;
}

.submit-btn {
  display: block;
  width: 100%;
  padding: 10px;
  font-size: 16px;
  font-weight: bold;
  color: white;
  background-color: #3498db;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: 0.3s ease-in-out;
}

.submit-btn:hover {
  background-color: #2980b9;
}
</style>