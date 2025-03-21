<template>
  <div class="upload-container">
    <div class="upload-card">
      <h1 class="title">Upload Your Video</h1>
      <form>
        <!-- VIDEO Viewer -->
        <div class="form-group">
          <label for="gif-view">VIDEO Preview</label>
          <img
            id="gif-view"
            class="gif-preview"
            src="https://www.adorama.com/alc/wp-content/uploads/2021/05/bird-wings-flying-feature.gif"
            alt="Bird Wings Flying"
          />
        </div>
  
        <!-- Title Field -->
        <div class="form-group">
          <label for="video-title">Title</label>
          <input type="text" id="video-title" placeholder="Enter video title" class="input" />
        </div>
  
        <!-- Detail Field -->
        <div class="form-group">
          <label for="video-detail">Detail</label>
          <textarea id="video-detail" placeholder="Enter video details" class="textarea"></textarea>
        </div>
  
        <!-- Dropdown Fields -->
        <div class="form-group">
          <label for="category">Clinic</label>
          <select id="category" class="dropdown">
            <option value="">Select Clinic</option>
            <option value="education">Clinic M</option>
            <option value="entertainment">Clinic Aaa</option>
            <option value="sports">Clinic จมูก</option>
          </select>
        </div>
  
        <div class="form-group">
          <label for="visibility">Course</label>
          <select id="visibility" class="dropdown">
            <option value="">Select Course</option>
            <option value="public">Course A</option>
            <option value="private">Course B</option>
          </select>
        </div>
  
        <!-- Submit Button -->
        <button type="submit" class="submit-btn">Submit</button>
      </form>
    </div>
  </div>
  </template>
  
  <script>
  export default {
  name: "UploadPage",
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
  
  .title {
  margin-bottom: 20px;
  font-size: 24px;
  font-weight: bold;
  text-align: center;
  }
  
  .form-group {
  margin-bottom: 15px;
  }
  
  label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
  }
  
  .gif-preview {
  display: block;
  max-width: 100%;
  height: auto;
  border: 1px solid #dcdcdc;
  border-radius: 4px;
  }
  
  .input,
  .textarea,
  .dropdown {
  width: 100%;
  padding: 8px;
  border: 1px solid #dcdcdc;
  border-radius: 4px;
  font-size: 14px;
  }
  
  .textarea {
  resize: vertical;
  height: 100px;
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