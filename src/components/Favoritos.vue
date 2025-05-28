<template>
  <section id="favoritos" class="favorites">
    <div class="section-title">
      <h2>MEUS POKÉMON FAVORITOS</h2>
    </div>
    <div class="pokemon-slider">
      <div class="slider-container" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
        <div class="pokemon-card" v-for="(pokemon, index) in pokemons" :key="index">
          <div class="pokemon-img">
            <img v-if="pokemon.icon.endsWith('.gif')" :src="pokemon.icon" alt="pokemon gif" />
            <i v-else :class="pokemon.icon"></i>
          </div>
          <div class="pokemon-name">{{ pokemon.name }}</div>
          <div class="pokemon-type">{{ pokemon.type }}</div>
          <p class="pokemon-description">{{ pokemon.description }}</p>
        </div>
      </div>
    </div>
    <div class="slider-nav">
      <div
        class="slider-dot"
        v-for="(dot, index) in pokemons.length"
        :key="index"
        :class="{ active: currentIndex === index }"
        @click="currentIndex = index"
      ></div>
    </div>
  </section>
</template>
<script>
import charizardIcon from '../assets/charizard_icon.gif';
import umbreonIcon from '../assets/pikachu.gif';
import pikachuIcon from '../assets/umbreon.gif';
import laprasIcon from '../assets/lapras.gif';
export default {
  name: 'Favorites',
  data() {
    return {
      currentIndex: 0,
      pokemons: [
        {
          icon: charizardIcon,
          name: "Charizard",
          type: "Fogo/Voador",
          description:
            "Um Pokémon que é sem dúvidas um dos meus favoritos! Tanto por seu design, tanto pela nostalgia. Sem contar sua Mega-Evolução X, que é simplesmente perfeita!"
        },
        {
          icon: umbreonIcon,
          name: "Pikachu",
          type: "Elétrico",
          description:
            "Um pouco quanto clichê, mas ainda sim, não possi negar que ele é um dos meus favoritos, como assisto o anime a muito tempo, a nostalgia tem sua parte na sua classificação no raking, entretando, gosto muito dele!"
        },
        {
          icon: pikachuIcon,
          name: "Umbreon",
          type: "Sombrio",
          description:
            "Não apenas minha Eveelution favorita, mas também meu Pokémon favorito de todos! Amo o jeito que ele parece um gatinho preto, os olhos, e etc. Além do poder ofensivo que ele tem :)"
        },
        {
          icon: laprasIcon,
          name: "Lapras",
          type: "Água/Gelo",
          description:
            "Um Pokémon que eu conheci assistindo o anime, e assim que o vi, entrou no meu top 10 favoritos rapidinho! Com o tempo, ele for crescendo no ranking, e hoje é um dos meus top 3 favoritos!"
        }
      ]
    };
  },
  mounted() {
    this.startAutoPlay();
  },
  beforeDestroy() {
    if (this.interval) {
      clearInterval(this.interval);
    }
  },
  methods: {
    startAutoPlay() {
      this.interval = setInterval(() => {
        this.currentIndex = (this.currentIndex + 1) % this.pokemons.length;
      }, 5000);
    }
  }
};
</script>

<style scoped>
.favorites {
  padding: 100px 0;
  background-color: var(--pokemon-white);
  position: relative;
}

.pokemon-slider {
  max-width: 1000px;
  margin: 0 auto;
  overflow: hidden;
  min-height: 520px; /* Altura aumentada */
}

.slider-container {
  display: flex;
  transition: transform 0.5s ease;
}

.pokemon-card {
  min-width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  text-align: center;
  box-sizing: border-box;
}

.pokemon-img {
  width: 200px;
  height: 200px;
  background: var(--pokemon-light-gray);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 5rem;
  color: var(--pokemon-red);
  margin-bottom: 20px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
}

.pokemon-img img {
  max-width: 100%;
  max-height: 100%;
  width: auto;
  height: auto;
  object-fit: contain;
}

.pokemon-name {
  font-weight: 800;
  font-size: 2rem;
  color: var(--pokemon-black);
  margin-bottom: 10px;
  font-family: 'Press Start 2P', cursive;
}

.pokemon-type {
  display: inline-block;
  background-color: var(--pokemon-light-gray);
  color: var(--pokemon-black);
  padding: 8px 20px;
  border-radius: 30px;
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 20px;
}

.pokemon-description {
  max-width: 600px;
  margin: 0 auto 20px auto;
  font-size: 1.1rem;
  color: var(--pokemon-gray);
  line-height: 1.6;
}

.slider-nav {
  margin-top: 20px;
  display: flex;
  justify-content: center;
  gap: 10px;
}

.slider-dot {
  width: 15px;
  height: 15px;
  background: var(--pokemon-light-gray);
  border-radius: 50%;
  cursor: pointer;
  transition: all 0.3s ease;
}

.slider-dot.active {
  background: var(--pokemon-red);
  transform: scale(1.2);
}

@media (max-width: 768px) {
  .pokemon-img {
    width: 150px;
    height: 150px;
    font-size: 3.5rem;
  }
}
</style>
