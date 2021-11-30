<template>
  <v-carousel
    cycle
    height="680"
    hide-delimiter-background
    show-arrows-on-hover
  >
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel>
</template>

<script>
  export default {
    data () {
      return {

        items: [
          {
            src: 'http://www.constructoraoviedo.com/wp-content/uploads/cable-via-12-960x430.jpg',
          },
        ],
      }
    },
  }
</script>
