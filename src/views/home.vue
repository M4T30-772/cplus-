<template>
 <div class="background-container">
<div class="home-page">

    <div class="welcome-message">
      <h1>Dobrodošli u C PLUS +</h1>
      <p>Programiranje je vještina budućnosti i visoko tražena na tržištu rada. Razvijajte kreativno razmišljanje i unaprijedite svoje logičko razmišljanje, što će vas odvesti na novu razinu rješavanja problema.</p>
      <p>Učenje kodiranja pomaže vam poboljšati logičko razmišljanje i odvesti vas na novu razinu rješavanja problema.</p>
    </div>

<div class="reasons-to-learn">
        <h2>Zašto učiti programirati?</h2>
        <ul>
          <li>Poboljšajte analitičke vještine i logičko razmišljanje.</li>
          <li>
            Otvorite vrata kreativnosti kroz stvaranje vlastitih digitalnih
            rješenja.
          </li>
          <li>
            Postanite konkurentniji na tržištu rada s traženjem vještina
            programiranja.
          </li>
        </ul>
      </div>

<div class="Login">
<h2>Prijavite se i odmah započnite sa učenjem</h2>
<div class="login-form">
      <h2>Registracija</h2>
      <form @submit.prevent="login">
        <label for="username">Ime i prezime:</label>
        <input type="text" id="username" v-model="username" required>
        <label for="password">Lozinka:</label>
        <input type="password" id="password" v-model="password" required>
        <label for="password">Ponovite lozinku:</label>
        <input type="password" id="password" v-model="password" required>
        <label for="password">Gmail:</label>
        <input type="password" id="password" v-model="gmail" required>
        
        <button type="submit">Prijava</button>
      </form>
    </div>
</div>

    <div class="course-info">
      <div class="beginner-course">
        <h2>Početnički tečaj</h2>
        <p>Prilagođen za one koji žele naučiti osnove programiranja u programu C++.</p>
        <router-link to="/learn" class="blue-button">Saznajte više</router-link>
      </div>

      <div class="advanced-course">
        <h2>Napredni tečaj</h2>
        <p>Namijenjen programerima koji žele bolje razumjeti napredne koncepte u C++.</p>
        <router-link to="/learn" class="blue-button">Saznajte više</router-link>
      </div>
    </div>
</div>
 </div>
</template>

<style scoped>
.background-container {
  background-color: #b3e0f2;
}
.home-page {
  max-width: 800px;
  margin: 0 auto;
  padding: 30px;
  background-color: #b3e0f2;
}

.welcome-message {
  text-align: center;
  margin-bottom: 30px;
}

h1, h2 {
  color: #333;
}

p {
  line-height: 1.6;
  color: #666;
}

.course-info {
  display: flex;
  justify-content: space-between;
}

.beginner-course, .advanced-course {
  width: 48%;
}


router-link {
  display: block;
  margin-top: 10px;
  color: #3498db;
  text-decoration: none;
  font-weight: bold;
}

router-link:hover {
  color: #3498db;
}

.login-form {
text-align: center;
  margin: 0 auto; 
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h2 {
  text-align: center;
  color: #333;
}

label {
  display: block;
  margin-bottom: 8px;
}

input {
  width: 100%;
  padding: 8px;
  margin-bottom: 16px;
  box-sizing: border-box;
}

button {
  background-color: #3498db;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  align-content: center;
}

button:hover {
  background-color: #2980b9;
}
.blue-button {
  background-color: #3498db;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  text-decoration: none; 
  display: inline-block; 
}

.blue-button:hover {
  background-color: #2980b9;
}
</style>
