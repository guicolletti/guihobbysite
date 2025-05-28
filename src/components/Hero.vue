<template>
  <section id="inicio" class="hero">
    <div class="hero-content">
      <h1>MEU MUNDO POKÉMON</h1>
      <p>Uma jornada minimalista através dos jogos, cartas e animações que moldaram minha vida</p>
      <a href="#hobbies" class="btn">Explorar Hobbies</a>
    </div>
  </section>
</template>

<style scoped>
.hero {
  background-image: url("../assets/pkmn_bg.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  padding: 120px 0 80px;
  text-align: center;
  overflow: hidden;
}

.hero::before {
  content: "";
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 1;
}

.hero * {
  position: relative;
  z-index: 2;
}

.hero-content {
  max-width: 900px;
  margin: 0 auto;
  padding: 0 20px;
}

.hero h1 {
  font-family: 'Press Start 2P', cursive;
  font-size: 3.5rem;
  color: var(--pokemon-red);
  margin-bottom: 20px;
  line-height: 1.2;
}

.hero p {
  font-size: 1.4rem;
  color: var(--pokemon-white);
  margin-bottom: 40px;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

@media (max-width: 992px) {
  .hero h1 {
    font-size: 2.5rem;
  }
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2rem;
  }

  .hero p {
    font-size: 1.1rem;
  }
}

@media (max-width: 576px) {
  .hero {
    padding: 80px 0 50px;
  }

  .hero h1 {
    font-size: 1.5rem;
  }

  .btn {
    padding: 12px 25px;
    font-size: 1rem;
  }
}
</style>