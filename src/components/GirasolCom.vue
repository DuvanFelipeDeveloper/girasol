<template>
  <div>
    <div ref="fireworksContainer" class="fireworks-container"></div>
    <div class="center-text">La verdad, quisiera estar regalándote girasoles ya, pero como no puedo, te los envío por acá. ¡Feliz Año! Antes de que te emborraches o me emborrache, espero que cumplas todas tus metas y que este año te traiga muchas bendiciones y alegrías. Ojalá pronto nos veamos y pueda regalarte unos girasoles de verdad.</div>
    <img src="@/assets/girasol.png" alt="Girasol" class="ramo-image" />

    <!-- Contenedor para el ramo de girasoles -->
    <div class="ramo-container">
      <img src="@/assets/girasol2.png" alt="Girasol" class="girasol-image" />
    </div>
  </div>
</template>

<script>
import fireworks from "fireworks-js";

export default {
  mounted() {
    const container = this.$refs.fireworksContainer;
    const fireworkOptions = {
      maxRockets: 3,
      rocketSpawnInterval: 150,
      numParticles: 100,
      explosionMinHeight: 0.2,
      explosionMaxHeight: 0.9,
      explosionChance: 0.08,
      width: window.innerWidth,
      height: window.innerHeight,
    };

    const firework = new fireworks(container, fireworkOptions);
    firework.start();
  },
};
</script>

<style scoped>
/* Estilos existentes */

html, body {
  height: 50%;
  margin: 0;
  overflow: hidden;
}

.fireworks-container {
  position: relative;
  background-color: black;
  height: 25vh; /* Establece la altura al 100% de la ventana */
  overflow: hidden; /* Oculta el desplazamiento vertical */
}

.center-text {
  position: absolute;
  top: 50%;
  left: 55%;
  transform: translate(-50%, -50%);
  color: white;
  font-size: 24px;
  font-weight: bold;
  animation: moveText 5s ease-in-out infinite;
}

.ramo-container {
  position: absolute;
  top: 5%; /* Ajusta la posición vertical según sea necesario */
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  z-index: 2; /* Asegura que el ramo esté por encima de la otra imagen */
}

.ramo-image {
  width: 500px; /* Ajusta el tamaño según sea necesario */
  height: auto;
  margin: 0 5px; /* Ajusta el margen entre las imágenes */
}

.girasol-container {
  position: absolute;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
}

.girasol-image {
  width: 2500px; /* Ajusta el tamaño según sea necesario */
  height: auto;
  margin: 0 1px; /* Ajusta el margen entre las imágenes */
}
</style>
