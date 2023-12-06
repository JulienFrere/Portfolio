<template>
  <Transition name="modal-fade">
    <div v-if="isOpen" class="modal-overlay">
      <div class="modal">
        <span class="close" @click="$emit('close')">&times;</span>
        <!-- Contenu de la modal -->
        <slot />
      </div>
    </div>
  </Transition>
</template>

<script setup>
defineProps(["isOpen"]);
</script>

<style scoped>
/* Styles pour l'arrière-plan foncé et la modal */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7); /* Augmentation de l'opacité pour un arrière-plan plus foncé */
  display: flex;
  justify-content: center;
  align-items: center;
  backdrop-filter: blur(5px); /* Effet de flou pour un arrière-plan plus moderne */
}

/* Style pour la boîte de la modal */
.modal {
  position: relative;
  background-color: #fff;
  padding: 40px; /* Augmentation de l'espacement pour un aspect plus aéré */
  border-radius: 10px; /* Bords plus arrondis */
  width: 80%;
  max-width: 800px; /* Ajustement de la largeur maximale */
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.3); /* Ombre plus prononcée pour un effet de profondeur */
  transition: opacity 0.3s ease;
}

/* Style pour le bouton de fermeture */
.close {
  position: absolute;
  top: 20px; /* Ajustement de la position du bouton de fermeture */
  right: 20px; /* Ajustement de la position du bouton de fermeture */
  cursor: pointer;
  font-size: 24px; /* Légère augmentation de la taille du bouton de fermeture */
  color: #333; /* Modification de la couleur pour plus de contraste */
  transition: color 0.3s ease; /* Ajout d'une transition de couleur pour un effet plus fluide */
}

.close:hover {
  color: #f00; /* Changement de couleur au survol pour un feedback visuel */
}

/* Styles pour l'animation de la modal */
.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.3s ease;
}

.modal-fade-enter-from,
.modal-fade-leave-to {
  opacity: 0;
}
</style>
