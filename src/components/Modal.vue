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
/* Style pour l'arrière-plan foncé et la modal */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7); 
  display: flex;
  justify-content: center;
  align-items: center;
  backdrop-filter: blur(5px); 
}

/* Style pour la boîte de la modal */
.modal {
  position: relative;
  background-color: #fff;
  padding: 40px; 
  border-radius: 10px; 
  width: 80%;
  max-width: 800px; 
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.3); 
  transition: opacity 0.3s ease;
}

/* Style pour le bouton de fermeture */
.close {
  position: absolute;
  top: 20px; 
  right: 20px; 
  cursor: pointer;
  font-size: 24px; 
  color: #333; 
  transition: color 0.3s ease; 
}

.close:hover {
  color: #f00; 
}

/* Style pour l'animation de la modal */
.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.3s ease;
}

.modal-fade-enter-from,
.modal-fade-leave-to {
  opacity: 0;
}
</style>
