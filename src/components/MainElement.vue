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
    description: "Mon premier projet était un CV, après avoir assimilé les bases du HTML et du CSS, le projet était principalement là pour montrer l'acquisition de compétences, ici c'étais le fonctionnement d'un projet en HTML5 ainsi que CSS3 pour la mise en forme",
    img: "../images/CVentier.png",
    technologies: "HTML et CSS",
    githubLink: "https://github.com/JulienFrere/cv.git",
    createdAt: "20 Octobre 2023",
    additionalPhotos: [
      "/src/assets/images/CvPhotoHeader.png",
      "/src/assets/images/CvLogoAction.png",
      "/src/assets/images/CvLogoFooter.png"
    ],
  },
  {
    title: "Projet d'espace commentaire dynamique en HTML, CSS et JavaScript",
    description: "Mon second projet avait pour but de dynamiser un espace commentaire à l'aide de JavaScript, la consigne étant de pouvoir afficher un commentaire qui s'actualiserait de manière immediate, donc dynamiquement, il s'agissait de ma première utilisation du JavaScript.",
    img: "../images/dynamique1.png",
    technologies: "HTML , CSS et JavaScript",
    githubLink: "https://github.com/JulienFrere/ExerciceDynamiser.git",
    createdAt: "14 Novembre 2023",
    additionalPhotos: [
      "/src/assets/images/dynamique1.png",
      "/src/assets/images/dynamique4.png"
    ],
  },
  // Futur projet ! 
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

/* Style pour le container des projets */
#MyProjects h2 {
  font-size: xx-large;
  text-align: center; 
  margin-top: 400px; 
  margin-bottom: 60px; 
  font-family:'Barlow', sans-serif;
}

.projects-container {
  display: flex;
  flex-wrap: wrap; 
  gap: 30px; 
  max-width: 800px; 
  margin: 0 auto; 
  margin-bottom: 200px;
  align-items: center;
  justify-content: center;
  font-family:'Barlow', sans-serif;
}

/* Style pour la grille de projets existante */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
  max-width: 800px;
  margin: 0 auto;
}

/* style pour ajuster la taille des images */
.projects-grid .project .project-image img {
  max-width: 100%;
  max-height: 200px; 
  width: auto;
  height: auto;
  align-items: center;
}

/* Style pour chaque projet individuel */
.project {
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
  overflow: hidden;
}

</style>
