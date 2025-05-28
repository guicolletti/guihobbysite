<template>
  <section id="hobbies" class="hobbies">
    <div class="section-title">
      <h2>MEUS HOBBIES</h2>
    </div>
    <div class="hobbies-grid">
      <div class="hobby-card" v-for="(hobby, index) in hobbies" :key="index" ref="hobbyCards">
        <div class="hobby-header">{{ hobby.title }}</div>
        <div class="hobby-content">
          <h3>{{ hobby.subtitle }}</h3>
          <p>{{ hobby.description }}</p>
          <div class="game-icons">
            <div class="game-icon" v-for="(icon, i) in hobby.icons" :key="i">
              <i :class="icon"></i>
            </div>
          </div>
          <p>{{ hobby.additional }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Hobbies',
  data() {
    return {
      hobbies: [
        {
          title: "JOGOS DE VIDEOGAME",
          subtitle: "Explorando as Regiões",
          description: "Minha jornada começou com Pokémon Fire & Red com emuladores de Game Boy Color no celular. Desde então, explorei todas as regiões, de Kanto a Paldea. Meus jogos favoritos:",
          icons: ["fas fa-fire", "fas fa-leaf", "fas fa-water"],
          additional: "Pokémon Legends: Arceus trouxe uma revolução na jogabilidade, enquanto Pokémon Scarlet/Violet expandiram o conceito de mundo aberto."
        },
        {
          title: "POKÉMON TCG FÍSICO",
          subtitle: "Coleção e Batalhas",
          description: "Coleciono cartas físicas desde 2016. Adora coleçar e principmente jogar, as vezes em pequenos torneios locais, mas meus decks ainda não se comparam aos profissionais.",
          icons: ["fas fa-solid fa-sheet-plastic", "fas fa-trophy", "fas fa-dice"],
          additional: "Participo mensalmente de torneios locais e eventos especiais da Pokémon Company."
        },
        {
          title: "TCG ONLINE & POCKET",
          subtitle: "Jogabilidade Digital",
          description: "Pokémon TCG Online permite batalhas com jogadores de todo o mundo. Com o novo Pokémon TCG Pocket, a experiência ficou ainda mais acessível.",
          icons: ["fas fa-mobile-alt", "fas fa-laptop", "fas fa-globe"],
          additional: "As mecânicas de coleta e batalha digital complementam perfeitamente o TCG físico."
        },
        {
          title: "SÉRIE ANIMADA",
          subtitle: "A Jornada de Ash",
          description: "Acompanho a série desde o primeiro episódio! O anime trouxe os Pokémon à vida com personagens memoráveis e batalhas épicas.",
          icons: ["fas fa-tv", "fas fa-film", "fas fa-star"],
          additional: "Meus arcos favoritos: Liga Laranja, Batalha da Fronteira e a conquista do título de Campeão Mundial!"
        }
      ]
    }
  },
  mounted() {
    this.animateCards();
    window.addEventListener('scroll', this.animateCards);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.animateCards);
  },
  methods: {
    animateCards() {
      const cards = this.$refs.hobbyCards;
      if (cards) {
        cards.forEach(card => {
          const rect = card.getBoundingClientRect();
          const isVisible = rect.top < window.innerHeight - 50 && rect.bottom >= 0;
          if (isVisible) {
            card.classList.add('visible');
          }
        });
      }
    }
  }
}
</script>

<style scoped>
.hobbies {
  padding: 100px 0;
  background-color: var(--pokemon-light-gray);
  position: relative;
}

.hobbies-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  position: relative;
  z-index: 2;
}

.hobby-card {
  background-color: var(--pokemon-card-bg);
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
  transition: all 0.5s ease;
  transform: translateY(50px);
  opacity: 0;
}

.hobby-card.visible {
  transform: translateY(0);
  opacity: 1;
}

.hobby-header {
  background: linear-gradient(to right, var(--pokemon-red), var(--pokemon-dark-red));
  color: var(--pokemon-white);
  padding: 20px;
  text-align: center;
  font-family: 'Press Start 2P', cursive;
  font-size: 1.3rem;
}

.hobby-content {
  padding: 30px;
  color: var(--pokemon-black);
}

.hobby-content h3 {
  color: var(--pokemon-black);
  margin-bottom: 15px;
  font-size: 1.5rem;
  font-weight: 700;
}

.hobby-content p {
  margin-bottom: 20px;
  font-size: 1.1rem;
  color: var(--pokemon-gray);
}

.game-icons {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 20px;
}

.game-icon {
  width: 60px;
  height: 60px;
  background: var(--pokemon-white);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.8rem;
  color: var(--pokemon-red);
  transition: all 0.3s ease;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
}

.game-icon:hover {
  transform: rotate(15deg) scale(1.1);
  background: var(--pokemon-red);
  color: var(--pokemon-white);
}
</style>