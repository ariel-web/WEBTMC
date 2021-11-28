<template>
  <div justify="center" align="center">
    <Inicio/>
    <template>
      <v-parallax
        src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
      ></v-parallax>
    </template>
    <h1 class="centered">Scroll me</h1>
    <div v-scroll="handleScroll" class="box">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. A atque amet
        harum aut ab veritatis earum porro praesentium ut corporis. Quasi
        provident dolorem officia iure fugiat, eius mollitia sequi quisquam.
      </p>
    </div>
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
      ></v-parallax>
    </template>
  </div>
</template>
<script>
import axios from "axios";
import Post from "../components/Post.vue";
import Inicio from "../components/inicio";
export default {
  components: {
    Post: Post,
    Inicio: Inicio,
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
          "opacity: 1; transform: translate3d(0, -10px, 0)"
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



</style>
