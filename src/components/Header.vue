<template>
  <header>
    <div class="header-container">
      <a href="#" class="logo">
        <div class="pokeball-icon">
          <div class="pokeball-button"></div>
        </div>
        <div class="logo-text">POKÉMON</div>
      </a>
      <nav>
        <ul>
          <li><a href="#inicio" :class="{ active: activeSection === 'inicio' }" @click="setActive('inicio')">Início</a></li>
          <li><a href="#sobre" :class="{ active: activeSection === 'sobre' }" @click="setActive('sobre')">Jornada</a></li>
          <li><a href="#hobbies" :class="{ active: activeSection === 'hobbies' }" @click="setActive('hobbies')">Hobbies</a></li>
          <li><a href="#favoritos" :class="{ active: activeSection === 'favoritos' }" @click="setActive('favoritos')">Favoritos</a></li>
          <li><a href="#contato" :class="{ active: activeSection === 'contato' }" @click="setActive('contato')">Contato</a></li>
        </ul>
      </nav>
    </div>
  </header>
</template>
<script>
export default {
  name: 'Header',
  data() {
    return {
      activeSection: 'inicio'
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      const sections = ['inicio', 'sobre', 'hobbies', 'favoritos', 'contato'];
      let current = '';

      sections.forEach(section => {
        const element = document.getElementById(section);
        if (element) {
          const rect = element.getBoundingClientRect();
          if (rect.top <= 100 && rect.bottom >= 100) {
            current = section;
          }
        }
      });

      if (current) {
        this.activeSection = current;
      }
    },
    setActive(section) {
      this.activeSection = section;
    }
  }
}
</script>
<style scoped>
header {
  background: linear-gradient(to right, var(--pokemon-red), var(--pokemon-dark-red));
  padding: 15px 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.header-container {
  width: 90%;
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 15px;
  text-decoration: none;
  animation: bounce 2s infinite;
}

.pokeball-icon {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: linear-gradient(to bottom, var(--pokemon-red) 0% 50%, var(--pokemon-white) 50% 100%);
  position: relative;
  border: 3px solid var(--pokemon-black);
  box-shadow: inset 0 2px 0 var(--pokemon-black), inset 0 -2px 0 var(--pokemon-black);
  display: flex;
  align-items: center;
  justify-content: center;
}

.pokeball-icon::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 0;
  width: 100%;
  height: 4px;
  background-color: var(--pokemon-black);
  transform: translateY(-50%);
}

.pokeball-button {
  width: 16px;
  height: 16px;
  background: var(--pokemon-white);
  border: 3px solid var(--pokemon-black);
  border-radius: 50%;
  z-index: 2;
  box-shadow: inset 0 0 0 2px var(--pokemon-gray);
}

.logo-text {
  font-family: 'Press Start 2P', cursive;
  color: var(--pokemon-white);
  font-size: 1.5rem;
  letter-spacing: 1px;
}

nav ul {
  display: flex;
  list-style: none;
  gap: 30px;
}

nav a {
  color: var(--pokemon-white);
  text-decoration: none;
  font-weight: 600;
  font-size: 1.1rem;
  padding: 8px 15px;
  transition: all 0.3s ease;
  position: relative;
  text-transform: uppercase;
  letter-spacing: 1px;
}

nav a:hover,
nav a.active {
  transform: translateY(-3px);
}

nav a::after {
  content: "";
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 100%;
  height: 3px;
  background-color: var(--pokemon-white);
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

nav a:hover::after {
  transform: scaleX(1);
}

/* ANIMAÇÃO BOUNCE */
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-5px);
  }
}

/* RESPONSIVO */
@media (max-width: 768px) {
  .header-container {
    flex-direction: column;
    gap: 20px;
  }

  nav ul {
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>