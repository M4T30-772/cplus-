<template>
<div class="main-page">
    <div class="grid-title beginner-title"> POČETNIČKI TEČAJ </div>
    
  <div class="grid-container">
    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <h2>Osnove c++</h2>
      <p> U ovome poglavlju ćete naučiti osnovne pojmove u programskom jeziku C++.  </p>
      <button @click="goToOsnove">Započni</button>
    </div>

    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <h2> Varijable </h2>
      <p>U ovome poglavlju ćete naučiti kako se služiti varijablama u programskom jeziku C++. </p>
      <button @click="goToVarijable">Započni</button>
    </div>

    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <h2>Ispis i upis teksta</h2>
      <p>U ovome poglavlju ćete naučiti kako unijeti teksta i ispisati tekst u programskom jeziku C++. </p>
      <button @click="goToInput">Započni</button>
    </div>

    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <h2>Strings </h2>
      <p>U ovome poglavlju ćete naučiti stringove u programskom jeziku C++.</p>
      <button @click="goToStrings">Započni</button>
    </div>

    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <h2>Petlje</h2>
      <p>U ovome poglavlju ćete naučiti kako koristiti petlje i koje petlje postoje u programskom jeziku C++. </p>
      <button @click="goToPetlje">Započni</button>
    </div>

    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <h2>Switch i break</h2>
      <p>U ovome poglavlju ćete naučiti kako koristiti switch i break u programskom jeziku C++. </p>
      <button @click="goToSwitch">Započni</button>
    </div>
  </div>
</div>
      <div class="grid-title advanced-title">NAPREDNI TEČAJ</div>

       <div class="grid-container">
    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <p>Funkcije</p>
      <button @click="goToMultipleChoice">Započni</button>
    </div>

    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <p>Klase</p>
      <button @click="goToWriteTheAnswer">Započni</button>
    </div>

    <div class="grid-item">
      <img src="@/assets/c plus +.png" alt="Grid Image">
      <p>Napredni koncepti u c++</p>
      <button @click="buttonClick(1)">Započni</button>
    </div>
       </div>
</template>

<<script>
export default {
  methods: {
    goToOsnove() {
      this.$router.push('/osnove');
    },
    goToVarijable() {
      this.$router.push('/varijable');
    },
    goToInput() {
      this.$router.push('/input');
    },
    goToStrings() {
      this.$router.push('/strings');
    },
    goToPetlje() {
      this.$router.push('/petlje');
    },
    goToSwitch() {
      this.$router.push('/switch');
    }
  },
};
</script>


<style scoped>

.grid-title {
  background-color: #3498db;
  padding: 20px;
  
}

.grid-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin-top: 20px;  
background-color: #fff;
}

/* nediraj ovo */
.grid-item {
  width: calc(32% - 20px);  
  margin: 20px 10px 20px;
  text-align: center;
  border: 2px solid #000;
  position: relative;
}
.grid-title {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 10px;
}
.grid-item img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
}

button {
  background-color: #3498db;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #2980b9;
}


</style>

