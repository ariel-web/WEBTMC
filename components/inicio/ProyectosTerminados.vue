<template>
  <v-container>
    <v-carousel hide-delimiters cycle>
      <template v-for="(item, index) in slider">
        <v-carousel-item
          v-if="(index + 1) % columns === 1 || columns === 1"
          :key="index"
        >
          <v-row class="flex-nowrap" style="height:90%;">
            <template v-for="(n, i) in columns">
              <template v-if="+index + i < slider.length">
                <v-col :key="i">
                  <v-sheet v-if="+index + i < slider.length" width="95%" height="100%" style=" box-shadow: rgba(0, 0, 0, 0.19) 0px 10px 20px, rgba(0, 0, 0, 0.23) 0px 6px 6px; border-radius:5px; " >
                    <div style="overflow:hidden; background:red; height:70%; border-radius:5px 5px 0px 0px;">
                      <img class="zoom" :src="slider[+index + i].imagen" width="100%" height="100%" />
                    </div>
                    <div style="margin-top:20px; width:90%;">
                      <span style="line-height: 35px; font-weight:300;"> {{slider[+index+i].title }}</span>
                    </div>
                  </v-sheet>
                </v-col>
              </template>
            </template>
          </v-row>
        </v-carousel-item>
      </template>
    </v-carousel>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    model: 0,
    slider: [
      {
        imagen: "https://ejuca.com/wp-content/uploads/2015/06/thumbnail.jpg",
        title: "Supermercado LIDL en León",
      },
      {
        imagen:
          "https://ejuca.com/wp-content/uploads/2021/06/lidl1bpx-1200x805.jpg",
        title: "CICAP, Centro Tecnológico Agroalimentario en Pozoblanco (Córdoba).",
      },
      {
        imagen:
          "https://ejuca.com/wp-content/uploads/2021/06/lidl1bpx-1200x805.jpg",
        title: "Reformas integrales en edificio de viviendas en c/ Ayala, Madrid.",
      },
      {
        imagen: "https://ejuca.com/wp-content/uploads/2015/06/thumbnail.jpg",
        title: "Reformas integrales en edificio de viviendas en c/ Ayala, Madrid.",
      },
      {
        imagen:
          "https://ejuca.com/wp-content/uploads/2021/06/lidl1bpx-1200x805.jpg",
        title: "Supermercado LIDL en León",
      },
      {
        imagen:
          "https://ejuca.com/wp-content/uploads/2021/06/lidl3px-1200x803.jpg",
        title: "CICAP, Centro Tecnológico Agroalimentario en Pozoblanco (Córdoba).",
      },
    ],
  }),
  computed: {
    columns() {
      if (this.$vuetify.breakpoint.xl) {
        return 4;
      }

      if (this.$vuetify.breakpoint.lg) {
        return 3;
      }

      if (this.$vuetify.breakpoint.md) {
        return 2;
      }

      return 1;
    },
  },
};
</script>
<style>
.zoom {
    transition: transform .5s;

}
.zoom:hover {
    transform: scale(1.2);
}

</style>
