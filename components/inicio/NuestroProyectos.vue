<template>
  <v-row>
    <v-col
      v-for="n in 6"
      :key="n"
      class="d-flex child-flex"
      cols="12" sm="12" sx="12" md="4"
    >
      <div style="padding:5px; border-radius:15px; object-fit: cover;">
      <v-img
        style="border-radius: 4px; box-shadow: #0000003d 3.4px 4.4px 14.2px;"
        :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
        :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
        aspect-ratio="1"
        class="grey lighten-2"
      >
      </v-img>
      </div>
    </v-col>
  </v-row>
</template>
