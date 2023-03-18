<template>
    <v-app-bar app color="black" dark>
      <v-app-bar-nav-icon color="#FF4858" v-show="mobile" @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="slogan" :class="{ 'slogan-mobile': mobile,'slogan-desktop': !mobile}">Naiara Oliveira</v-toolbar-title>
      <!--    <v-spacer/>-->
      <div class="pr-11" :hidden="mobile">
        <v-btn class="btn" to="/sobre" color="#FF4858">Sobre</v-btn>
        <v-btn class="btn" o="/projetos" color="#FF4858">Projetos</v-btn>
        <v-btn class="btn" to="/contato" color="#FF4858">Contato</v-btn>
      </div>
  
    </v-app-bar>
  
    <v-navigation-drawer v-model="drawer" app temporary :hidden="!mobile">
      <hr/>
  
      <div class="pa-2" >
        <router-link to="/" class="btn d-block mb-2">Home</router-link>
        <router-link to="/projetos" class="btn d-block mb-2">Projetos</router-link>
        <router-link to="/contato" class="btn d-block mb-2">Contato</router-link>
      </div>
  
    </v-navigation-drawer>
    <v-container fluid class="container-imagem-texto">
  <v-row>
    <v-col cols="12" md="5" class="d-flex align-center justify-center">
      <div>
        <h1 class="text-h5 mb-4">Olá mundo!</h1>
        <h2 class="text-h6 mb-6">Developer front-end</h2>
        <v-btn color="primary" depressed>Conheça mais</v-btn>
      </div>
    </v-col>
    <v-col cols="12" md="7" class="col-padding">
      <v-img class="img-container fill-width" src="@/assets/istockphoto-510160569-612x612.jpg" cover="true"></v-img>
    </v-col>
  </v-row>
</v-container>

<section class="about">
    <v-container>
      <v-row>
        <v-col cols="12" md="6">
          <v-img src="@/assets/istockphoto-510160569-612x612.jpg" alt="Image description" width="100%" height="90vh"></v-img>
        </v-col>
        <v-col class="text-body-1 text-sm-body-1">
          <div class="text">
            <h2>Sobre</h2>
            <p>Olá, meu nome é Naiara e sou estudante de Sistemas de Informação do Campus Coxim da UFMS, atualmente cursando o 7º semestre. Eu tenho uma paixão especial pela área de desenvolvimento frontend e já desenvolvi projetos acadêmicos e pessoais que me permitiram aprimorar minhas habilidades em HTML, CSS e JavaScript, assim como o framework Vue.js. Estou ansiosa para poder aplicar meu conhecimento e entusiasmo em um ambiente de trabalho profissional.</p>
            <p>Sou uma pessoa organizada e focada, que sempre traça objetivos claros e trabalha com metas estabelecidas. Além disso, acredito que um bom trabalho é feito em equipe e estou sempre disposta a ajudar e colaborar. Minha motivação é construir soluções efetivas para o mercado.</p>
            <p>Meu objetivo profissional é adquirir a experiência que o mercado exige e me transformar em uma das melhores desenvolvedoras do mercado.</p>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </section>

  <section>
    <v-container>
        <h1 class="text-h6 mb-4">Projetos</h1>
    <v-row class="cards">
      <v-col v-for="(project, index) in projects" :key="index" cols="12" sm="6" md="4" lg="3">
        <v-card class="card">
          <v-img :src="project.image" height="400px"></v-img>
          <v-card-title>{{ project.title }}</v-card-title>
          <v-card-text>{{ project.description }}</v-card-text>
          <v-card-actions>
            <v-btn text>Ver projeto</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
</v-container>
</section>



  <v-footer class="footer">
    <v-container align-items="center">
      <v-row>
        <v-col align="center" ml-5 mb-2 cols="12" md="8">
              Desenvolvido por Naiara Oliveira
        </v-col>

        <v-col cols="12" md="4" mb-2>
    <v-btn icon href="https://github.com/seugithub">
      <v-icon size="48">mdi-github</v-icon>
    </v-btn>
    <v-btn icon href="https://www.linkedin.com/in/seulinkedin">
      <v-icon size="48">mdi-linkedin</v-icon>
    </v-btn>
    <v-btn icon href="mailto:seuemail@exemplo.com">
      <v-icon size="48">mdi-email</v-icon>
    </v-btn>
  
        </v-col>
       
      </v-row>
    </v-container>
  </v-footer>

  </template>
  
  <script>
  

  export default {
    name: 'HomeView',
   
    data: () => ({
      mobile: false,
      drawer: true,
      projects: [
        {
          title: "Projeto 1",
          description: "Descrição do projeto 1",
          image: "data:image/png;base64,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",
        },
        {
          title: "Projeto 2",
          description: "Descrição do projeto 2",
          image: "https://www.x-apps.com.br/static/67db5fb3350275672b3565b2c152c970/d6fb3/css-html-javascript.jpg",
        },
        {
          title: "Projeto 3",
          description: "Descrição do projeto 3",
          image: "https://www.uniquenewsonline.com/wp-content/uploads/2020/08/Front-End-Projects.png",
        },
        {
          title: "Projeto 4",
          description: "Descrição do projeto 4",
          image: "https://raw.githubusercontent.com/vivadecora/projeto-front-end-vivadecora-nao-fazer-fork/master/screenshots-readme/screenshot-desktop-inicial.png?raw=true",
        },
      ],
     
    }),
    mounted() {
      this.mobile = this.verificarMobile();
      window.addEventListener('resize', this.handleResize);
    },
    beforeUnmount() {
      window.removeEventListener('resize', this.handleResize);
    },
    methods: {
      verificarMobile() {
        return window.innerWidth < 768;
      },
      handleResize() {
        this.mobile = this.verificarMobile();
      }
    }
  
  }
  </script>
  
  <style scoped>
  
  .slogan {
    text-transform: uppercase;
    color:#FF4858;
  }
  
  .slogan-mobile {
    text-align: center;
  }
  
  .slogan-desktop {
    padding-left: 7%;
  }
  
  .btn {
    text-decoration: none;
    color:#FF4858;
    background-color: black;
    text-align: center;
    border-radius: 50px;
  }
  
  .btn:hover {
    background-color: #1a1a1a;
    border: white 2px solid;
  }
  .text h2{
    font-size: 2.5rem;
    font-family: 'Courier New', Courier, monospace !important;
    color: rgba(0,0,0,0.9);
    text-align: center !important;
  }
.text p{
    font-size:1.6rem;
    font-family: 'Courier New', Courier, monospace !important;
    color: rgba(0,0,0,0.7);
    font-weight: 400;
    line-height: 1.2;
    margin-bottom: 1.5rem;
    text-align:inherit !important;
    margin-top: 50px;
    
}

.v-img {
  border-radius: 8px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}
.container-imagem-texto .col-padding {
  height: auto;
  max-height: 88vh; 
}

.col-padding{
    padding: 0px !important;
}
.container-imagem-texto{
    padding:0;
}

.text-h5 {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.text-h6 {
  font-size: 1.5rem;
  font-weight: normal;
  margin-bottom: 2rem;
}

.v-btn {
  font-size: 1rem;
  padding: 0.75rem 2rem;
}
.thumbnail-one {
  background-image: url("../assets/projeto1.png");
  background-size: cover;
  height: 200px;
}

.thumbnail-two {
  background-image: url("../assets/projeto2.png");
  background-size: cover;
  height: 200px;
}

.thumbnail-three {
  background-image: url("../assets/projeto3.jpg");
  background-size: cover;
  height: 200px;
}

.thumbnail-four {
  background-image: url("../assets/projeto4l.png");
  background-size: cover;
  height: 200px;
}
.about {
  padding: 50px 0;
}
.text {
  padding: 20px;
}


.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.card {
  margin-bottom: 24px;
  width: 100%;
}

.v-image__image {
  object-fit: cover;
}
.card:hover {
  transform: scale(1.05);
}
.card:hover::after {
  content: "";
  display: block;
  height: 4px;
  width: 100%;
  background-color: red;
  position: absolute;
  bottom: 0;
  left: 0;
  animation: grow 0.3s ease-in-out forwards;
}
@keyframes grow {
  from {
    transform: scaleX(0);
  }
  to {
    transform: scaleX(1);
  }
}

.text-body-1 {
  font-size: 16px;
  line-height: 1.5;
}

.text-sm-body-1 {
  font-size: 14px;
}

@media only screen and (max-width: 600px) {
  .text-body-1 {
    font-size: 14px;
  }

  .text-sm-body-1 {
    font-size: 12px;
  }
}
.v-footer{
   margin-top:15px;
   margin-bottom:30px;
   color: rgba(0,0,0.9);
   font-size: 1.5rem !important;
}
  </style>