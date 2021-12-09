<template>
  <div justify="center" align="center">
    <div style="margin-bottom: -12px">
      <Inicio />
    </div>

    <v-section class="sectionIndex" id="actividades">
      <div style="padding-top: 20px; padding-bottom: 20px">
        <span class="titleSection">Nuestra Empresa</span>
        <hr class="lineahr" />
      </div>
      <div class="container">
        <Nosotros />
      </div>
    </v-section>

    <v-section>
      <div>
        <Ambiente/>
      </div>
    </v-section>

    <section>
      <template>
        <v-parallax height="">
          <div style="padding-top: 20px">
            <span class="titleSection">Nuestros proyectos</span>
            <hr class="lineahr" />
          </div>
          <div class="container">
            <NuestrosProyectos style="margin-bottom: 20px" />
          </div>
        </v-parallax>
      </template>
    </section>

    <section style="padding-top: 2.3rem">
      <v-parallax
        class="servicios"
        v-bind:src="require('../assets/imagenes/edificio1.jpg')"
      >
        <Servicios />
      </v-parallax>
    </section>

    <v-section>
      <div style="padding-top: 20px">
        <span class="titleSection">Proyectos Finalizados</span>
        <hr class="lineahr" />
      </div>
      <ProyectosTerminados />
    </v-section>
  </div>
</template>
<script>
import axios from "axios";
import Post from "../components/Post.vue";
import Inicio from "../components/inicio";
import Nosotros from "../components/inicio/Nosotros.vue";
import NuestrosProyectos from "../components/inicio/NuestroProyectos.vue";
import ProyectosTerminados from "../components/inicio/ProyectosTerminados.vue";
import Servicios from "../components/inicio/Servicios.vue";
import Ambiente from "../components/inicio/Ambiente.vue";

export default {
  components: {
    Post: Post,
    Inicio: Inicio,
    Nosotros: Nosotros,
    NuestrosProyectos: NuestrosProyectos,
    ProyectosTerminados: ProyectosTerminados,
    Servicios: Servicios,
    Ambiente:Ambiente,
  },
  data() {
    return {
      posts: [],
      icons: ["mdi-rewind", "mdi-play", "mdi-fast-forward"],
      items: [
        {
          title: "New Releases",
          text: `It's New Release Friday`,
          subtext: "Newly released songs. Updated daily.",
          img: "../assets/imagenes/edificio1.jpg",
        },
        {
          title: "Rock",
          text: "Greatest Rock Hits",
          subtext: "Lose yourself in rock tunes.",
          img: "https://images.unsplash.com/photo-1498038432885-c6f3f1b912ee?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2100&q=80",
        },
        {
          title: "Mellow Moods",
          text: "Ambient Bass",
          subtext: "Chill beats to mellow you out.",
          img: "https://images.unsplash.com/photo-1542320868-f4d80389e1c4?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=3750&q=80",
        },
        {
          title: "Mellow Moods",
          text: "Ambient Bass",
          subtext: "Chill beats to mellow you out.",
          img: "https://images.unsplash.com/photo-1542320868-f4d80389e1c4?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=3750&q=80",
        },
      ],
      transparent: "rgba(255, 255, 255, 0)",
    };
  },

  methods: {
    handleScroll: function (evt, el) {
      if (window.scrollY > 50) {
        el.setAttribute(
          "style",
          "opacity: 1; transform: translate3d(0, -10px, 0);"
        );
      }
      //return window.scrollY > 100;
    },
  },
  async created() {
    try {
      const res = await axios.get("https://jsonplaceholder.typicode.com/posts");
      this.posts = res.data;
    } catch (error) {
      console.log(error);
    }
  },
};
</script>

<style>
.sectionIndex[id] {
  scroll-margin-top: 110px;
}

html {
  scroll-behavior: smooth;
}
.titleSection {
  font-size: 2.3rem;
  color: black;
  font-weight: 300;
}
.lineahr {
  margin-top: 0.2rem;
  margin-bottom: 2rem;
  height: 0.25rem;
  width: 160px;
  background-color: red;
  border: none;
}
.servicios {
  width: 100%;
  height: 600px !important;
  margin: 0px;
  padding: 0px;
}

.element {
  margin-left: -1000px;
  animation-name: stretch;
  animation-duration: 6.5s;
  animation-timing-function: ease-in;
  animation-direction: alternate;
  animation-iteration-count: infinite;
  animation-play-state: running;
}
.element2 {
  animation-name: stret;
  animation-duration: 6.5s;
  animation-timing-function: ease-in;
  animation-direction: alternate;
  animation-iteration-count: infinite;
  animation-play-state: running;
}
.conten {
  display: flex;
  margin-bottom: 10px;
  margin-left: 20px;
}

.div-ambiente{
  display: flex;
}


@media (max-width: 600px) {
  .servicios {
    background: teal;
    width: 100%;
    height: 100% !important;
    animation-play-state: paused;
  }

  .div-ambiente{
    display: block;
  }
}
</style>
