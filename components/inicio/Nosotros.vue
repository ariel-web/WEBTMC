<template>
  <div>
  <v-row no-gutters>
    <v-col cols="12" sm="6" md="4">
      <div style="height:100%;">
        <router-link to="/">
              <v-img
                alt="Vuetify Logo"
                contain
                v-bind:src="require('../../assets/imagenes/TMCLOGO.png')"
                class="imgLogoPrincipal"
                style=" width:60%;"
              />
        </router-link>

      </div>
    </v-col>
    <v-col cols="12" md="8">
     <div style="">
        <div>
          <h2 style="font-weight:300; font-size:2.5rem;">BIENVENIDOS</h2>
        </div>
        <div style="padding:1rem;">
            <p class="Inicialnosotros" style="font-weight:300;">
              Con la visión de consolidar el crecimiento industrial y
              económico de nuestro país nace CONSTRUCTORA INSUR hace más de 37 años,
              conformado por un grupo de especialistas en cada área que compone el
              roceso de construcción de plantas industriales, naves y edificios
              comerciales, respondiendo en de manera profesional Y trabajando en
              equipo con nuestros clientes para resolver y crear proyectos que superen
              sus expectativas, convirtiendo grandes ideas en grandes construcciones.
              sus expectativas, convirtiendo grandes ideas en grandes construcciones.
            </p>
         </div>
      </div>
    </v-col>
  </v-row>

    <v-row no-gutters style="background:#000000d2; padding:0.8rem 0px">
    <v-col cols="12" sm="6" md="4">
      <div style="height:100%;">
      </div>
    </v-col>
    <v-col cols="12" md="8">
      <div style=";  padding:1rem;" >
        <div style="display:flex;" >
          <div>
            <router-link to="/nosotros">
            <button style=" background:#b2b0b0; border-radius:8px; border: solid 1px grey; color:black; padding:5px 15px 5px 15px;">

              Ver más
            </button>
            </router-link>
          </div>
          <div>
            <button style=" margin-left:20px; background:red; border-radius:8px; border: solid 1px grey; padding:5px 15px 5px 15px; color:white;" >Descargar CV</button>
          </div>
        </div>

      </div>
    </v-col>
  </v-row>
  </div>
</template>
<style>
.Inicialnosotros{
  text-align: justify;
  line-height: 35px;
  color:black;
}

.Inicialnosotros::first-letter {
  color: red;
  margin: 0 .3rem 0 0;
  font-weight: 600;
  font-size: 4.1rem;
  float: left;
  line-height: 1;


}
</style>
