<script setup>
import MainElement from '../components/MainElement.vue'
import MyContact from '../components/MyContact.vue'
import { ref } from 'vue';

const showModal = ref(false);

const toggleModal = (value) => {
  showModal.value = value;
};


</script>

<template>
  <main>
    <div id="WelcomeItem">
    <h1>Bienvenue sur mon Portfolio !</h1>
    <p>
      Bonjour à tous ! Je m'appelle Julien Frere et je suis apprenti développeur web en formation. Passionné par le monde du développement, je suis constamment en quête de
      nouvelles connaissances et de défis excitants dans ce domaine en évolution permanente!
    </p>
  </div>
  <div class="main-element-container">
    <MainElement :showModal="showModal" :toggleModal="toggleModal" />
    </div>
    <MyContact /> 
  </main>
</template>

<style scoped>
#WelcomeItem {
  position: absolute; /* Utilisation de la position absolue */
  top: 150px; /* Ajuster la position verticale selon vos besoins */
  left: 20px;
  right: 20px;
  text-align: center;
  font-size: medium;
  display: flex;
  flex-direction: column;
  align-items: center;
  color: black;
  padding: 20px;
  box-sizing: border-box;
  z-index: 1; /* Assurer que l'élément est au-dessus de l'image de fond si nécessaire */
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

#WelcomeItem h1,
#WelcomeItem p {
  display: block;
  margin-bottom: 10px;
}

/* Ajoutez un style pour la classe main-element-container */
.main-element-container {
  margin-top: 300px; /* Augmentation de l'espace entre les éléments */
}

/* Styles pour MainElement */
/* Redimensionnez la police et ajoutez de l'espace autour du texte */
#MyProjects {
  font-size: small; /* Réduction de la taille de la police */
  margin: 20px 50px; /* Ajout d'espace autour du texte */
  /* Ajoutez d'autres styles si nécessaire */
}
</style>
