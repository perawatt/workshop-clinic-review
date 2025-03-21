<template>
  <div class="login-container">
    <div class="login-card">
      <h1 class="title">Loing</h1>
      <p class="subtitle">เข้าสู่ระบบ Clinic Review</p>
      <button class="social-btn google-btn" @click="onClickLogin">Login with Google</button>
      <!-- <button class="social-btn facebook-btn">Login with Facebook</button> -->
    </div>
  </div>
</template>

<script lang="ts" setup>
// export default {
//   name: "LoginPage",
// };
definePageMeta({
  layout: 'login',
});
const onClickLogin = () => {
  navigateTo('home')
};
</script>

<style scoped>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 60vh;
  background-color: #f5f6fa;
  font-family: 'Arial', sans-serif;
}

.login-card {
  background: white;
  border-radius: 8px;
  padding: 20px 30px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  max-width: 400px;
  width: 100%;
}

.title {
  margin: 0;
  font-size: 24px;
  font-weight: bold;
}

.subtitle {
  color: #7f8c8d;
  margin: 10px 0 20px;
  font-size: 16px;
}

.social-btn {
  display: block;
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  font-size: 16px;
  font-weight: bold;
  border-radius: 4px;
  cursor: pointer;
  transition: 0.3s ease-in-out;
  border: none;
}

.google-btn {
  background: #db4437;
  color: white;
}

.facebook-btn {
  background: #3b5998;
  color: white;
}

.social-btn:hover {
  opacity: 0.9;
}
</style>