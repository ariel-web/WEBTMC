<template>
  <div>
    <v-section style="margin: 0px">
      <v-parallax
        height="300"
        v-bind:src="require('../assets/imagenes/edificio1.jpg')"
      >
        <div
          style="
            height: 300px;
            margin: 0px;
            padding-bottom: 20px;
            display: flex;
            align-items: end;
            justify-content: center;
            margin-left: -20px;
            margin-right: -20px;
            background: #0000007d;
          "
        >
          <div class="">
            <div style="display: flex; justify-content: center">
              <span
                class="titleSection"
                style="
                  color: white;
                  font-size: 2.1rem;
                  font-weight: 300;
                "
                >Proyectos Terminados</span
              >
            </div>
            <div style=" display: flex; justify-content: center" >
              <hr style="height:6px; width:200px; background:red; border:none;" />
            </div>
          </div>
        </div>
      </v-parallax>
    </v-section>
      <div class="containerFinalizados">

          <v-timeline :dense="izquierda">
            <v-timeline-item
              v-for="(year, i) in years"
              :key="i"
              :color="year.color"
              small
            >
              <template v-slot:opposite>

              <div class="py-4">
                <img
                    width="100%" height="220"
                    v-bind:src="require('../assets/imagenes/imagen1.jpg')"
                  />
              </div>
              </template>
              <div class="py-4">
                <h2 :class="`headline font-weight-light mb-4 ${year.color}--text`">
                  Lorem ipsum
                </h2>
                <div style="text-align:justify;">
                  Lorem ipsum dolor sit amet, no nam oblique veritus. Commune
                  scaevola imperdiet nec ut, sed euismod convenire principes at. Est
                  et nobis iisque percipit, an vim zril disputando voluptatibus, vix
                  an salutandi sententiae.
                </div>
              </div>
            </v-timeline-item>
          </v-timeline>

      </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    responsiveOptions: [
			{
				breakpoint: '1024px',
				izquierda: false,
				numScroll: 3
			},
			{
				breakpoint: '600px',
				numVisible: 2,
				numScroll: 2
			},
			{
				breakpoint: '480px',
				izquierda:true,
				numScroll: 1
			}
		],
    years: [
      {
        color: "cyan",
        year: "1960",
      },
      {
        color: "green",
        year: "1970",
      },
      {
        color: "pink",
        year: "1980",
      },
      {
        color: "amber",
        year: "1990",
      },
      {
        color: "orange",
        year: "2000",
      },
    ],
  }),
};
</script>

<style>
.containerFinalizados{
  width:65%;
  margin:auto;

}
@media (max-width: 600px) {
 .containerFinalizados{
   width: 100%;
  }
}

</style>
