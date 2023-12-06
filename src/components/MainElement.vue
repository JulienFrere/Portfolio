<template>
  <div id="MyProjects">
    <h2>Mes projets</h2>
    <div class="projects-container">
      <!-- Utilisation de v-for pour afficher les projets -->
      <Project v-for="(project, index) in projects" :key="index" :project="project" class="project" />
    </div>
  </div>
</template>

<script setup>
import Project from "../components/Project.vue";
const projects = [
  {
    title: "Projet de CV en HTML et CSS",
    description: "Mon premier projet était un CV, après avoir assimilé les bases du HTML et du CSS",
    img: "./images/CVentier.png",
    technologies: "HTML et CSS",
    githubLink: "https://github.com/JulienFrere/cv.git",
    createdAt: "20 Octobre 2023",
  },
  {
    title: "Projet d'espace commentaire dynamique en HTML, CSS et JavaScript",
    description: "Mon second projet avait pour but de dynamiser un espace commentaire à l'aide de JavaScript",
    img: "./images/dynamique1.png",
    technologies: "HTML , CSS et JavaScript",
    githubLink: "https://github.com/JulienFrere/ExerciceDynamiser.git",
    createdAt: "14 Novembre 2023",
  },
  // Ajoute ici les autres projets de manière similaire
  {
    title: "Futur projet...",
    description: "Description du nouveau projet",
    img: "./images/comingsoonspace.jpeg",
    technologies: "Coming Soon !",
    createdAt: "Un jour peut-être !",
  },
];
</script>

<style scoped>
/* Styles pour la container des projets */
#MyProjects h2 {
  font-size: xx-large;
  text-align: center; /* Centrer horizontalement */
  margin-top: 400px; /* Ajouter de l'espace en haut */
  margin-bottom: 60px; /* Ajouter de l'espace en bas */
}

.projects-container {
  display: flex;
  flex-wrap: wrap; /* Permettre le retour à la ligne si nécessaire */
  gap: 30px; /* Espacement entre les projets */
  max-width: 800px; /* Largeur maximale des projets */
  margin: 0 auto; /* Centrer les projets horizontalement */
  margin-bottom: 200px;
  align-items: center;
  justify-content: center;
}

/* Garde tes styles pour la grille de projets existante */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
  max-width: 800px;
  margin: 0 auto;
}

/* Nouveaux styles pour ajuster la taille des images */
.projects-grid .project .project-image img {
  max-width: 100%;
  max-height: 200px; /* Ajuste la hauteur maximale selon tes préférences */
  width: auto;
  height: auto;
  align-items: center;
}

/* Styles pour chaque projet individuel */
.project {
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
  overflow: hidden;
}
</style>
