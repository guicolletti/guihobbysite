<template>
  <section id="sobre" class="about">
    <div class="section-title">
      <h2>MINHA JORNADA</h2>
    </div>
    <div class="about-content">
      <div class="about-text">
        <h3>Treinador Pokémon desde 1999</h3>
        <p>Minha aventura no mundo Pokémon começou quando ganhei meu primeiro Game Boy Color e uma cópia de Pokémon
          Blue. Desde então, capturei, treinei e colecionei centenas de Pokémon através de nove gerações de jogos.</p>
        <p>Como um verdadeiro fã, meu hobby vai além dos jogos principais. Coleciono cartas TCG físicas desde 2002,
          participo de torneios locais, jogo o TCG Online diariamente e acompanho religiosamente a série animada desde o
          primeiro episódio exibido no Brasil.</p>
        <p>Pokémon Legends: Arceus revolucionou minha experiência com a série, enquanto Pokémon TCG Pocket trouxe uma
          nova dimensão para o jogo de cartas digital.</p>
      </div>
      <div class="about-image">
        <div class="pokeball-wrapper">
          <div class="rotating-pokeball">
            <div class="pokeball-button"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
.about {
  padding: 100px 0;
  background-color: var(--pokemon-white);
  position: relative;
}

.about-content {
  display: flex;
  gap: 60px;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.about-text {
  flex: 1;
}

.about-text h3 {
  font-size: 2rem;
  margin-bottom: 25px;
  color: var(--pokemon-black);
  font-weight: 700;
}

.about-text p {
  margin-bottom: 20px;
  font-size: 1.1rem;
  line-height: 1.8;
  color: var(--pokemon-gray);
}

.about-image {
  flex: 1;
  text-align: center;
}

/* POKÉBOLA */
.pokeball-wrapper {
  width: 300px;
  height: 300px;
  margin: 0 auto;
  animation: rotate 8s linear infinite;
}

.rotating-pokeball {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: linear-gradient(to bottom, var(--pokemon-red) 0% 50%, var(--pokemon-white) 50% 100%);
  position: relative;
  border: 8px solid var(--pokemon-black);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: inset 0 4px 0 var(--pokemon-black), inset 0 -4px 0 var(--pokemon-black);
}

.rotating-pokeball::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 0;
  width: 100%;
  height: 8px;
  background-color: var(--pokemon-black);
  transform: translateY(-50%);
  z-index: 1;
}

.pokeball-button {
  width: 60px;
  height: 60px;
  background: var(--pokemon-white);
  border: 6px solid var(--pokemon-black);
  border-radius: 50%;
  z-index: 2;
  box-shadow: inset 0 0 0 4px var(--pokemon-gray);
}

/* ROTAÇÃO */
@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

/* RESPONSIVO */
@media (max-width: 992px) {
  .about-content {
    flex-direction: column;
  }
}

@media (max-width: 768px) {
  .pokeball-wrapper {
    width: 200px;
    height: 200px;
  }

  .pokeball-button {
    width: 40px;
    height: 40px;
    border-width: 4px;
    box-shadow: inset 0 0 0 3px var(--pokemon-gray);
  }

  .rotating-pokeball::before {
    height: 6px;
  }
}
</style>
<script>
export default {
  name: 'AboutSection'
}
</script>
