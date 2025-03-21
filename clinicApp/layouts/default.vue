Code snippet

<template>
  <div class="layout">
    <header class="header">
      <div class="logo-container">
        <img src="https://img.freepik.com/free-vector/butterfly-colorful-logo-template_361591-1587.jpg" alt="Logo" class="logo" />
        <h1 class="site-title">Review Clinic App</h1>
      </div>
    </header>

    <nav class="navigation">
      <ul class="nav-list">
        <li class="nav-item">
          <nuxt-link to="home" class="nav-link">Home</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="userProfile" class="nav-link">Profile</nuxt-link>
        </li>
      </ul>
    </nav>

    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<style>
.layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.header {
  background-color: #f0f0f0;
  padding: 20px;
  text-align: center;
}

.logo-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo {
  max-height: 50px;
  margin-right: 10px;
}

.site-title {
  margin: 0;
}

.navigation {
  background-color: #2980B9;
  color: white;
  padding: 0px;
}

.nav-list {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: center;
}

.nav-item {
  margin: 0 15px;
}

.nav-link {
  color: white;
  text-decoration: none;
}

.content {
  flex-grow: 1;
  padding: 20px;
}
</style>