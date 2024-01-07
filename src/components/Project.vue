<template>
  <div class="project">
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    <button type="button" @click="isOpen = true"><img :src="project.img" alt="Image du projet" /></button>
    <!-- Ajoute ici d'autres détails du projet si nécessaire -->
  </div>
  <Modal :isOpen="isOpen" @close="isOpen = false">
    <h2>{{ project.title }}</h2>
    <p>Technologies utilisées: {{ project.technologies }}</p>
    <p>Lien vers le repository : <a :href="project.githubLink" target="_blank">Voir le code ! </a></p>
    <p>Date de création: {{ project.createdAt }}</p>
    <div v-if="project.additionalPhotos && project.additionalPhotos.length > 0">
        <p>Photos supplémentaires :</p>
        <div v-for="(photo, index) in project.additionalPhotos" :key="index">
          <img :src="photo" alt="Photo du projet"/>
        </div>
      </div>
    </Modal>
</template>

<script setup>
import { ref } from "vue";
import Modal from "./Modal.vue";
defineProps(["project"]);
const isOpen = ref(false);

const closeModalOutside = (event) => {
  if (!event.target.closest(".modal")) {
    isOpen.value = false;
  }
};

</script>

<style scoped>
.project img {
  width: 100%;
}
.project:hover {
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.4);
  cursor: pointer;
}

.project {
  transition: box-shadow 0.3s ease;
}


</style>
