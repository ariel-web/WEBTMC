<template>
  <div justify="center" align="center">
    <div style="margin-bottom: -12px">
      <Inicio />
    </div>

    <v-section class="sectionIndex" id="actividades">
      <div style="padding-top:20px; padding-bottom:20px;">
        <span class="titleSection">Nuestra Empresa</span>
        <hr class="lineahr">
      </div>
      <div class="container">
        <Nosotros/>
      </div>
    </v-section>

    <section>
    <template>
      <v-parallax
        height=""

      >
      <div style="padding-top:20px;">
        <span class="titleSection">Nuestros proyectos</span>
        <hr class="lineahr">
      </div>
      <div class="container">
          <NuestrosProyectos style="margin-bottom:20px;"/>
      </div>
      </v-parallax>
    </template>
    </section>


    <section style="padding-top:2.3rem;">
    <template>
      <v-parallax
        height="400"
        v-bind:src="require('../assets/imagenes/edificio1.jpg')"
        style="padding:0px;"
      >
      <div style="height:400px;  display:flex; align-items:center; text-align:left; margin-left:-20px; background: linear-gradient(60deg, #8b0000d2, transparent 85%);"  >

        <div class="container">
          <span class="titleSection" style="color:white; font-size:3.7rem; font-weight:300;" >Nuestros servicios</span>
          <p style="font-size:1.2rem;">Ofrecemos una alta gama de servicios y soluciones para distintas</p>
          <p style="font-size:1.2rem; margin-top:-20px;">empresas</p>
          <button class="black" style="padding:5px 20px 5px 20px">ver más </button>
        </div>

      </div>

      </v-parallax>
    </template>
    </section>


    <v-section >
      <div style="padding-top:20px;">
        <span class="titleSection">Proyectos Finalizados</span>
        <hr class="lineahr">
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
import NuestrosProyectos from "../components/inicio/NuestroProyectos.vue"
import ProyectosTerminados from "../components/inicio/ProyectosTerminados.vue";

export default {
  components: {
    Post: Post,
    Inicio: Inicio,
    Nosotros:Nosotros,
    NuestrosProyectos:NuestrosProyectos,
    ProyectosTerminados: ProyectosTerminados,
  },
  data() {
    return {
      posts: [],
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
</style>
