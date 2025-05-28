<template>
  <footer id="contato">
    <div class="footer-content">
      <div class="footer-section">
        <h3>MEU MUNDO POKÉMON</h3>
        <p>Uma jornada através dos jogos, cartas e animações que marcaram minha vida como treinador Pokémon.</p>
        <p>Design minimalista com paleta vermelho, branco, preto e cinza.</p>
      </div>

      <div class="footer-section">
        <h3>CONTATO</h3>
        <p><i class="fas fa-envelope"></i> treinador@pokemon.com</p>
        <p><i class="fas fa-phone"></i> +55 (11) 99999-8888</p>
        <p><i class="fas fa-map-marker-alt"></i> Cidade de Pallet, Kanto</p>
        <div class="social-links">
          <a href="#" class="social-link"><i class="fab fa-discord"></i></a>
          <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
          <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
          <a href="#" class="social-link"><i class="fab fa-youtube"></i></a>
        </div>
      </div>

      <div class="footer-section">
        <h3>LINKS RÁPIDOS</h3>
        <p><a href="#inicio" style="color: white;">Início</a></p>
        <p><a href="#sobre" style="color: white;">Minha Jornada</a></p>
        <p><a href="#hobbies" style="color: white;">Meus Hobbies</a></p>
        <p><a href="#favoritos" style="color: white;">Pokémon Favoritos</a></p>
      </div>
    </div>
    <div class="copyright">
      <p>&copy; 2023 Meu Mundo Pokémon. Esta é uma página de fã não oficial. Pokémon e seus respectivos nomes são marcas registradas da Nintendo, The Pokémon Company e Game Freak.</p>
    </div>
  </footer>
</template>

<style scoped>
footer {
  background: linear-gradient(to right, var(--pokemon-red), var(--pokemon-dark-red));
  color: var(--pokemon-white);
  padding: 70px 0 30px;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto 50px;
  padding: 0 20px;
}

.footer-section h3 {
  font-family: 'Press Start 2P', cursive;
  font-size: 1.3rem;
  margin-bottom: 25px;
  color: var(--pokemon-white);
  letter-spacing: 1px;
}

.footer-section p {
  margin-bottom: 15px;
  font-size: 1.05rem;
}

.social-links {
  display: flex;
  gap: 15px;
  margin-top: 20px;
}

.social-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 50px;
  height: 50px;
  background: var(--pokemon-white);
  border-radius: 50%;
  color: var(--pokemon-red);
  font-size: 1.5rem;
  transition: all 0.3s ease;
  text-decoration: none;
}

.social-link:hover {
  transform: translateY(-5px) rotate(10deg);
  background: var(--pokemon-black);
  color: var(--pokemon-white);
}

.copyright {
  text-align: center;
  padding-top: 30px;
  max-width: 1200px;
  margin: 0 auto;
  font-size: 1rem;
  color: rgba(255, 255, 255, 0.8);
}
</style>