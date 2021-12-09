<template>
  <div
    style="
      height: 100%;
      display: flex;
      align-items: center;
      text-align: center;
      margin-left: -20px;
      background: #0000007d;
      margin-right: -20px;
      /* background: linear-gradient(60deg, #8b0000d2, transparent 85%); */
    "
  >
    <div class="container">
      <span
        class=""
        style="color: white; font-size: 2.7rem; font-weight: 300; margin-bottom:w0px;"
        >Nuestros servicios</span
      >
      <p style="font-size: 1rem">
        Nuestros servicios incluyen: Gerencia de Proyectos, Supervisión de
        Obras, Auditorias Técnicas y/o Económicas, Elaboración y/o Evaluación de
        Presupuestos, Supervisión Económica y/o Financiera de Proyectos y
        Supervisión y Auditoría de obras por impuestos.
      </p>
      <p style="font-size: 1rem; margin-top: -20px">empresas</p>

      <v-row class="fill-height" align="center" justify="center">
        <template v-for="(item, i) in items" style="">
          <v-col :key="i" cols="12" md="3">
            <div style="width: 100%; display: flex; justify-content: center">
              <v-hover v-slot="{ hover }">
                <v-card
                  :elevation="hover ? 12 : 2"
                  :class="{ 'on-hover': hover }"
                >
                  <div>
                    <v-avatar style="height: 170px; width: 170px">
                      <img
                        v-bind:src="
                          require('../../assets/imagenes/' + item.img)
                        "
                      />
                    </v-avatar>
                  </div>
                </v-card>
              </v-hover>
            </div>
            <div style="display: flex; justify-content: center">
              <div style="padding-top: 20px; width: 75%">
                <span> {{ item.text }} </span>
              </div>
            </div>
          </v-col>
        </template>
      </v-row>

        <v-btn
          v-click-outside="onClickOutside"
          :color="'#0000009d'"
          :dark="active"
          @click="active = true"
          style="margin-top: 40px;
          margin-bottom: 0px;
          padding: 20px 35px 20px 35px;
          border: solid #0000004d 1px;
          "

        >
        <span  class="text-lowercase" style="color:white;">ver mas</span>
        </v-btn>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      active: false,
      items: [
        {
          text: `Ejecución de obras integrales`,
          img: "computadora-gif.gif",
        },
        {
          text: `Desarrollo Integral de proyectos`,
          img: "archivos-gif.gif",
        },
        {
          text: `Gestión de proyectos`,
          img: "cubos.gif",
        },
        {
          text: `Supervisión de obras`,
          img: "cuaderno-gif.gif",
        },
      ],
      transparent: "rgba(255, 255, 255, 0)",
    };
  },
  methods: {
        onClickOutside () {
          this.active = false
        },
  },
};
</script>

<style>
.v-card {
  transition: opacity 0.4s ease-in-out;
  border-radius: 50%;
}

.v-card:not(.on-hover) {
  height: 220px;
  width: 220px;
  opacity: 0.4;
  padding: 20px;
  background: #ffffff5d;
  border-radius: 50%;
  border: solid 4px #ffffff3d;
}
.v-card.on-hover {
  height: 220px;
  width: 220px;
  padding: 20px;
  border-radius: 50%;
  background: #ffffff5b;
  border: solid 4px #ffffff3d;
}


</style>
