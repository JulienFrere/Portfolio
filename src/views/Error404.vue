<template>
  <div class="error-page">
    <h1>404 - Page non trouvée</h1>
    <p>Désolé, la page que vous recherchez est introuvable.</p>
    <!-- Utilisation d'un div pour l'image de fond -->
    <div class="error-image"></div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
/* Styles pour le composant Error404.vue */

.error-page {
  /* Centrage du contenu */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh; /* Hauteur de la fenêtre visible */
}

/* Style pour l'image de fond */
.error-image {
  width: 100%;
  height: 100%;
  /* Chemin vers votre image en arrière-plan */
  background: url("../assets/images/castlecherryblossom.jpg") center center/cover no-repeat;
}
</style>
