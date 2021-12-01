<template>
  <div justify="center" align="center">
    <div style="margin-bottom: -12px">
      <Inicio />
    </div>

    <v-section class="sectionIndex" id="actividades">
      <div style="padding-top:20px;">
        <span class="titleSection">NUESTRA EMPRESA</span>
        <hr class="lineahr">
      </div>
      <div class="container">
        <Nosotros/>
      </div>
    </v-section>


    <template>
      <v-parallax height="300" src="">
        <div v-for="item in posts" v-bind:key="item.id">
          <post :id="item.id" :name="item.title" />
          <pre v-animate-on-scroll>{{ item }}</pre>
        </div>
      </v-parallax>
    </template>

    <template>
      <v-parallax
        height="300"
        src="https://cdn.vuetifyjs.com/images/parallax/material2.jpg"
      >

      </v-parallax>
    </template>

    <v-section >
      <div style="padding-top:20px;">
        <span class="titleSection">PROYECTOS FINALIZADOS</span>
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
import ProyectosTerminados from "../components/inicio/ProyectosTerminados.vue";

export default {
  components: {
    Post: Post,
    Inicio: Inicio,
    Nosotros:Nosotros,
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
  font-size: 2.7rem;
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
