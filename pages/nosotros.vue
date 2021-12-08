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
            padding: 0px;
            display: flex;
            align-items: end;
            justify-content: center;
            margin-left: -20px;
            margin-right: -20px;
            background: #0000007d;
          "
        >
          <div>
            <span
              class="titleSection"
              style="color: white; font-size: 3.7rem; font-weight: 300"
              >Nosotros</span
            >
            <hr class="lineahr" style="margin-left: 20px" />
          </div>
        </div>
      </v-parallax>
    </v-section>

    <div
      style="
        margin: 0px;
        padding: 0px;
        display: flex;
        align-items: end;
        justify-content: center;
        margin-top: 20px;
      "
    >
      <div>
        <p
          class="titleSection"
          style="text-align: center; font-size: 2.3rem; font-weight: 300"
        >
          ¿Quienes Somos?
        </p>
      </div>
    </div>
    <div class="container">
      <p style="font-size: 1.2rem; text-align: justify; line-height: 2rem; font-weight:400;">
        Somos una organización liderada por empresarios peruanos que cuenta con
        16 años de experiencia en el mercado, dedicada al negocio inmobiliario a
        través del diseño, construcción y comercialización de viviendas
        multifamiliares en Lima. Contamos con un equipo de profesionales
        altamente capacitados y aplicamos las últimas técnicas y productos que
        se encuentran disponibles en la industria de la construcción.
      </p>
    </div>
    <div
      style="
        margin: 0px;
        padding: 0px;
        display: flex;
        align-items: end;
        justify-content: center;
      "
    >
      <div>
        <p
          class="titleSection"
          style="text-align: center; font-size: 2.3rem; font-weight: 300"
        >
          Visión
        </p>
      </div>
    </div>
    <div class="container">
      <p style="font-size: 1.2rem; text-align: justify; line-height: 2rem">
        Ser una empresa admirada por sus clientes, empleados y proveedores,
        responsable socialmente y líder en el mercado al que se dirige.
      </p>
    </div>

    <div
      style="
        margin: 0px;
        padding: 0px;
        display: flex;
        align-items: end;
        justify-content: center;
      "
    >
      <div>
        <p
          class="titleSection"
          style="text-align: center; font-size: 2.3rem; font-weight: 300"
        >
          Misión
        </p>
      </div>
    </div>
    <div class="container">
      <p style="font-size: 1.2rem; text-align: justify; line-height: 2rem">
        Contribuir con el desarrollo de las ciudades en las que operamos,
        entregando productos inmobiliarios de calidad e innovadores, y
        procurando la satisfacción total de nuestros clientes a través de un
        servicio integral y personalizado.
      </p>
    </div>

        <div
      style="
        margin: 0px;
        padding: 0px;
        display: flex;
        align-items: end;
        justify-content: center;
      "
    >
      <div>
        <p
          class="titleSection"
          style="text-align: center; font-size: 2.3rem; font-weight: 300"
        >
          Asociaciones que nos respaldan
        </p>
      </div>
    </div>
    <div class="container">
        <div class="text-center">
    <div>
      <v-btn
        class="ma-2"
        color="primary"
        dark
      >
        Accept
        <v-icon
          dark
          right
        >
          mdi-checkbox-marked-circle
        </v-icon>
      </v-btn>

      <v-btn
        class="ma-2"
        color="red"
        dark
      >
        Decline
        <v-icon
          dark
          right
        >
          mdi-cancel
        </v-icon>
      </v-btn>

      <v-btn
        class="ma-2"
        dark
      >
        <v-icon
          dark
          left
        >
          mdi-minus-circle
        </v-icon>Cancel
      </v-btn>
    </div>

    <div>
      <v-btn
        class="ma-2"
        color="orange darken-2"
        dark
      >
        <v-icon
          dark
          left
        >
          mdi-arrow-left
        </v-icon>Back
      </v-btn>

      <v-btn
        class="ma-2"
        color="purple"
        dark
      >
        <v-icon dark>
          mdi-wrench
        </v-icon>
      </v-btn>

      <v-btn
        class="ma-2"
        color="indigo"
        dark
      >
        <v-icon dark>
          mdi-cloud-upload
        </v-icon>
      </v-btn>
    </div>

    <div>
      <v-btn
        class="ma-2"
        text
        icon
        color="blue lighten-2"
      >
        <v-icon>mdi-thumb-up</v-icon>
      </v-btn>

      <v-btn
        class="ma-2"
        text
        icon
        color="red lighten-2"
      >
        <v-icon>mdi-thumb-down</v-icon>
      </v-btn>
    </div>
  </div>
    </div>
  </div>
</template>

<style>
.lineahr {
  margin-top: 0.2rem;
  margin-bottom: 2rem;
  height: 0.25rem;
  width: 200px;
  background-color: red;
  border: none;
}
</style>
