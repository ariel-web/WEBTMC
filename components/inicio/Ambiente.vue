<template>
  <div
        style="padding-top: 20px; padding-bottom: 20px; background: #000000e9"
      >
        <v-col cols="12" style="color:white;">
          <h1 style="font-weight:300; font-size:2.4rem; margin-top:10px; margin-bottom:20px;">Comprometidos con el medio ambiente</h1>
        </v-col>
        <v-row>
        <div class="container div-ambiente" style="margin-bottom:20px;">

          <v-col
            class="d-flex child-flex text-white"
            cols="12"
            sm="12"
            sx="12"
            md="5"
          >
            <div class="element" style="color: white; text-align: left">
              <div class="conten">
                <img
                  width="60px" height="60px"
                  style="margin-top:10px; margin-left:-10px;"
                  v-bind:src="require('../../assets/imagenes/hoja2.png')"
                />
                <span
                  class="texto-encima"
                  style="
                    font-size: 1.4rem;
                    font-weight: 500;
                    text-align: left;
                    color: white;
                    line-height: 2rem;
                  "
                  >Nos comprometemos con el <br />
                  desarrollo de
                  <span
                    style="color: green; font-size: 1.5rem; text-align: left"
                    >proyectos sostenibles</span
                  >
                  <hr
                    style="
                      height: 6px;
                      width: 100px;
                      border: none;
                      background: green;
                      margin-top: 10px;
                    "
                  />
                </span>

                </div>
                <span style="margin-top: 10px; line-height: 2rem">
                  Construimos hogares exzxficientes en el uso de recursos,
                  reduciendo el impacto ambiental y contribuyendo al ahorro de
                  las familias.
                </span>

            </div>
          </v-col>
          <v-col
            class="d-flex child-flex text-white"
            cols="12"
            sm="12"
            sx="12"
            md="2"
          >
            <img
              height="150"
              width="260"
              v-bind:src="require('../../assets/imagenes/hoja.png')"
            />
          </v-col>

          <v-col class="d-flex child-flex" cols="12" sm="12" sx="12" md="5">
            <div class="element2" style="color: white; justify-content: center">
              <span
                style="
                  font-size: 1.4rem;
                  font-weight: 500;
                  text-align: left;
                  color: white;
                "
                >Nos comprometemos con el <br />
                desarrollo de
                <span style="color: green; font-size: 1.5rem"
                  >proyectos sostenibles</span
                >
              </span>
              <hr
                style="
                  height: 7px;
                  width: 100px;
                  border: none;
                  background: green;
                  margin-top: 10px;
                  margin-bottom: 10px;
                "
              />
              <span>
                Construimos hogares eficientes en el uso de recursos, reduciendo
                el impacto ambiental y contribuyendo al ahorro de las familias.
              </span>
            </div>
          </v-col>
        </div>
        </v-row>

      </div>
</template>

<style>

.element {
  margin-left: -1000px;
  animation-name: stretch;
  animation-duration: 6.5s;
  animation-timing-function: ease-in;
  animation-direction: alternate;
  animation-iteration-count: infinite;
  animation-play-state: running;
}
.element2 {
  animation-name: stret;
  animation-duration: 6.5s;
  animation-timing-function: ease-in;
  animation-direction: alternate;
  animation-iteration-count: infinite;
  animation-play-state: running;
}
.conten {
  display: flex;
  margin-bottom: 10px;
  margin-left: 20px;
}

@keyframes stretch {
  0% {
    transform: translateX(10px);
    opacity: 0%;
  }
  25% {
    margin-left: 10px;
    opacity: 50%;
  }
  50% {
    margin-left: 10px;
    opacity: 100%;
  }
  75% {
    margin-left: 10px;
  }
  100% {
    margin-left: 10px;
  }
}

@keyframes stret {
  0% {
    opacity: 0%;
  }
  25% {
    opacity: 50%;
  }
  50% {
    opacity: 100%;
  }
  75% {
    opacity: 100%;
  }
  100% {
    opacity: 100%;
  }
}

</style>
