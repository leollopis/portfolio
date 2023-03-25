
<template>
    <div>
        <nav>
            <div class="nav-container">
                <div class="nav-left">
                <div class="logo">
                    <h2>Léo LLOPIS</h2>
                </div>
                </div>
                <div class="nav-center">
                <div class="nav-links">
                    <ul>
                    <li><a href="#" @click.prevent="scrollToProjects">Projets</a></li>
                    <li><a href="#">Contact</a></li>
                    <li>
                        <div class="separateur">
                            <a id="cv-anim" href="#oui" @click.prevent="showCV">CV</a>
                        </div>
                    </li>
                    </ul>
                </div>
                </div>
                <div class="nav-right">
                <h2>Portfolio</h2>
                </div>
            </div>
        </nav>
      <div class="content">
        <div id="oui" class="cv-container" v-if="showingCV">
          <img src="@/assets/cv.png" alt="CV">
          <input type="button" value="Télécharger le CV !" @click="pdf">
        </div>
        <div class="projects-container" ref="projectsContainer">
          <div class="project-section" v-for="(project, index) in projects" :key="index" :class="{'light-gray': index % 2 === 0, 'dark-gray': index % 2 === 1}">
            <img :src="project.imagePath" :alt="project.title">
            <div class="project-details">
              <h3>{{ project.title }}</h3>
              <p>{{ project.description }}</p>
            </div>
          </div>
        </div>
        <div class="section-container">
  <div class="section-title">
    <h2>Langages de programmation</h2>
  </div>
  <div class="section-list">
    <ul>
      <li>
        <img src="@/assets/html.png" alt="">
        <p>HTML</p>
      </li>
      <li>
        <img src="../assets/css.png" alt="">
        <p>CSS</p>
      </li>
      <li>
        <img src="../assets/js.png" alt="">
        <p>Javascript</p>
      </li>
      <li>
        <img src="../assets/php.png" alt="">
        <p>php</p>
      </li>
      <li>
        <img src="../assets/c++.png" alt="">
        <p>C++</p>
      </li>
    </ul>
  </div>
</div>

<div class="section-container">
  <div class="section-title">
    <h2>Technologies et logiciels utiles au développement web</h2>
  </div>
    <div class="section-list">
        <ul>
            <li>
                <img src="@/assets/symfony.svg" alt="">
                <p>Symfony</p>
            </li>
            <li>
                <img src="@/assets/logo.png" alt="">
                <p>Vue.js</p>
            </li>
            <li>
                <img src="@/assets/affinity.png" alt="">
                <p>Affinity</p>
            </li>
            <li>
                <img src="@/assets/git.png" alt="">
                <p>git</p>
            </li>
            <li>
                <img src="@/assets/Mysql.png" alt="">
                <p>MySQL</p>
            </li>
        </ul>
    </div>
</div>

<div class="section-container">
  <div class="section-title">
    <h2>Autres compétences</h2>
  </div>
  <div class="section-list">
    <ul>
      <li>
        <img src="@/assets/3dsmax.png" alt="">
        <p>3DS Max</p>
      </li>
      <li>
        <img src="@/assets/substance.png" alt="">
        <p>Substance</p>
      </li>
      <li>
        <img src="@/assets/unity.png" alt="">
        <p>Unity</p>
      </li>
    </ul>
  </div>
</div>
      </div>
    </div>
  </template>
  
  <script>
  import pdf from '@/assets/CV_LLOPIS_Leo_Dev_Web.pdf';
  export default {
    data() {
      return {
        showingCV: false,
        projects: [
          {
            title: "Comics More",
            imagePath: require('@/assets/comicsmore.png'),
            description: "Plateforme de vente et lecture de comics",
          },
          {
            title: "ASCII Art",
            imagePath: require('@/assets/asciiart.png'),
            description: "Programme C++ qui convertit les images en dessins \"ascii\"",
          },
          {
            title: "Comparaison Algorithmique",
            imagePath: require('@/assets/complexite.png'),
            description: "Programme C++ qui compare des algorithmes de tri sur des tableaux de tailles differentes",
          },
          {
            title: "Project DF",
            imagePath: require('@/assets/php.png'),
            description: "Jeux unity d'exploration de donjons dans l'univers Dark Fantaisy",
          },
        ],
      };
    },
    methods: {
      showCV() {
        this.showingCV = !this.showingCV;
      },
      scrollToProjects() {
        this.$refs.projectsContainer.scrollIntoView({ behavior: "smooth" });
      },
      pdf() {
        
        const link = document.createElement('a');
        link.href = pdf;
        link.download = 'CV_LLOPIS_Leo_Dev_Web.pdf';
        link.target = '_blank';
        link.click();
        }
    },
  }
  </script>
  
<style scoped>
body {
    overflow-x: hidden;
    margin: 0;
  }
  
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 20px 0px 20px 0px;
    background-color: #2a3d50;
    color: #fff;
  }
  
  .logo h2 {
    padding-left: 20px;
    margin: 0;
    font-size: 24px;
  }
  
  .nav-right h2 {
    margin: 0;
    font-size: 24px;
  }
  
  .nav-links {
    margin: 0 auto;
  }
  
  .nav-links ul {
    display: flex;
    flex-direction: row;
    list-style: none;
    margin: 0;
    padding: 0 10 0 10;
  }
  
  .nav-links li {
    margin: 0 10px;
  }
  
  .nav-links a {
    color: #fff;
    text-decoration: none;
  }
  
  /* Nouveaux styles ajoutés pour adapter la mise en page */
  .nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }
  
  .nav-left {
    width: 33.33%;
    display: flex;
    justify-content: flex-start;
  }
  
  .nav-center {
    width: 33.33%;
    display: flex;
    justify-content: center;
  }
  
  .nav-right {
    width: 33.33%;
    display: flex;
    justify-content: flex-end;
    padding-right:20px;
  }

  .content {
  padding-top: 80px;
}

.cv-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
  margin-bottom: 100px;
}

.cv-container input{
    margin-top: 70px;
    padding: 10px 30px;
    background: #2a3d50;
    color: white;
    border: solid black 2px;
    border-radius: 100px;
}

img {
  max-width: 100%;
  max-height: 100%;
}

.projects-container {
  width: 100%;
}

.project-section {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 40px;
  margin: 0 auto;
}

.project-section img {
  max-width: 10%;
  max-height: 50%;
}

.project-details {
  width: 45%;
}

.project-details h3 {
  font-size: 24px;
  margin-bottom: 10px;
}

.project-details p {
  font-size: 16px;
}

.light-gray {
  background-color: #f0f0f0;
}

.dark-gray {
  background-color: #c0c0c0;
}

.section-container {
  margin-top: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.section-title {
  margin-bottom: 20px;
}

.section-title h2 {
  font-size: 24px;
}

.section-list {
  display: flex;
  justify-content: center;
}

.section-list ul {
  display: flex;
  flex-direction: row;
  list-style: none;
  margin: 0;
  padding: 0;
}

.section-list li {
  margin: 0 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.section-list img {
  width: 50px;
  height: 50px;
  margin-bottom: 10px;
}

.section-list p {
  font-size: 16px;
  text-align: center;
}

@keyframes cvPute {
  0%{
    color:white
  }
  50%{
    color:black;
    font-weight: 500;
  }
  100%{
    color : white
  }
}

#cv-anim{
    animation-name: cvPute;
    position: sticky;
    animation-iteration-count: infinite;
    animation-duration: 1s;
}
</style>