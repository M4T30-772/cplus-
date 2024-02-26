<template>
  <div id="app">
    <nav class="navbar">
      <div class="container">
        <router-link to="/" class="logolink">
          <div class="logo-container">
            <img src="@/assets/c plus +.png" class="main-image">
            <div class="logo">C PLUS +</div>
          </div>
        </router-link>
        <div class="nav-links">
          <ul class="nav-list">
            <li class="nav-item">
              <router-link to="/" class="auth-link">HOME</router-link>
              <router-link to="/learn" class="auth-link">TEČAJI</router-link>
              <router-link to="/writeTheAnswerBeginner" class="auth-link">PRIMJER TESTA 1</router-link>
              <router-link to="/multipleChoiceBeginner" class="auth-link">PRIMJER TESTA 2</router-link>
            </li>
          </ul>
        </div>
        <div class="auth-links">
          <router-link to="/login" class="auth-link">PRIJAVA</router-link>
          <router-link to="/signup" class="auth-link">REGISTRACIJA</router-link>
        </div>
      </div>
    </nav>

    <router-view />

    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="contact-info">
            <p>Email: info@cplusplus.com</p>
            <p>Phone: +365 447 269</p>
          </div>
          <button class="notification-button">Get Notifications</button>
        </div>
        <p class="copyright">&copy; 2024 C PLUS +. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<style>
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh; 
  
}

.main-image {
  max-width: 100%;
  height: auto;
  max-height: 3rem;
}

.navbar {
  background-color: #000000;
  color: #fff;
  padding: 10px 0;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-container {
  display: flex;
  align-items: center;
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
  margin-left: 10px;
  color: #fff;
}
.logolink {
  text-decoration: none;
}

.logolink:hover {
  text-decoration: none;
}

.logolink.router-link-exact-active {
  text-decoration: none;
}
.nav-links {
  display: flex;
}

.nav-list {
  list-style: none;
  display: flex;
}

.nav-item {
  margin-right: 15px;
}

.nav-item a {
  text-decoration: none;
  color: #fff;
  font-weight: bold;
}

.nav-item a:hover {
  color: #ffcc00;
}

.auth-links {
  display: flex;
}

.auth-link {
  text-decoration: none;
  color: #fff;
  font-weight: bold;
  margin-left: 15px;
}

.auth-link:hover {
  color: #ffcc00;
}

body {
  margin: 0;
  font-family: 'Arial', sans-serif;
}

.footer {
  background-color: #fff;
  color: #333;
  padding: 20px 0;
  text-align: center;
  margin-top: auto; 
  margin-left: 10px;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.contact-info {
  text-align: left;
}

.contact-info p {
  margin: 5px 0;
  font-size: 14px;
}

.notification-button {
  background-color: #3498db;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
  margin-left: 15px;
}

.notification-button:hover {
  background-color: #2980b9;
}

.copyright {
  font-size: 12px;
  text-align: right; 
}
</style>
