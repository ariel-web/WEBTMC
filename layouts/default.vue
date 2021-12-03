<template>
  <v-app class="app">
    <div
      v-if="pos === 'uno'"
      style="z-index: 99; display: flex; justify-content: center"
      v-scroll="handleScroll"
      class="navbar"
    >
      <v-container class="containerbg">
        <div class="barrar_menu text-md-right" style="color: blue; box-shadow: none; ">
          <div
            class="d-flex align-center; "
            style="display: flex; justify-content: center; background:none; width:100px; "
          >
            <router-link to="/">
              <v-img
                alt="Vuetify Logo"
                contain
                v-bind:src="require('../assets/imagenes/TMCLOGO.png')"
                transition="scale-transition"
                class="imgLogo"
              />
            </router-link>
              <div style="position:absolute; bottom:0; font-size:0.8rem; color:white;">
                <span>TMC INTEGRAL SAC</span>
              </div>
          </div>

          <v-list
            dense
            flat
            class="d-none d-md-block right"
          >
            <v-list-item-group
              class="d-flex"
              style="background: transparent; align: right"
            >
              <v-list-item to="/">
                <v-list-item-content > INICIO </v-list-item-content>
              </v-list-item>

              <v-menu open-on-hover bottom offset-y>
                <template v-slot:activator="{ on, attrs }">
                  <v-list-item v-bind="attrs" v-on="on" href="/#actividades">
                    <v-list-item-content class="white--text"> NOSOTROS </v-list-item-content>
                  </v-list-item>
                </template>

                <v-list>
                  <v-list-item link to="/ponencias">
                    <v-list-item-title>Ponencias</v-list-item-title>
                  </v-list-item>
                  <v-list-item link to="/minicursos">
                    <v-list-item-title>Minicursos</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>

              <v-menu open-on-hover bottom offset-y>
                <template v-slot:activator="{ on, attrs }">
                  <v-list-item v-bind="attrs" v-on="on">
                    <v-list-item-content class="white--text" >SERVICIOS</v-list-item-content>
                  </v-list-item>
                </template>

                <v-list>
                  <v-list-item link href="/concursos/#destreza">
                    <v-list-item-title>Concurso de Destreza</v-list-item-title>
                  </v-list-item>
                  <v-list-item link href="/concursos/#investigacion">
                    <v-list-item-title
                      >Concurso de Investigación</v-list-item-title
                    >
                  </v-list-item>
                </v-list>
              </v-menu>

              <v-list-item href="/#colaboradores">
                <v-list-item-content class="white--text"> EXPERIENCIA </v-list-item-content>
              </v-list-item>
              <v-list-item href="/embajadores">
                <v-list-item-content class="white--text"> CLIENTES </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>

          <v-btn
            icon
            class="d-block d-md-none mr-3"
            @click="menu_drawer = !menu_drawer"
          >
            <v-icon large>mdi-menu</v-icon>
          </v-btn>
        </div>
      </v-container>
    </div>

    <v-navigation-drawer
      v-model="menu_drawer"
      absolute
      right
      class="d-md-none"
      style="z-index: 999;"
    >
      <v-row justify="end">
        <v-col cols="12" class="d-flex justify-end pr-3">
          <v-btn icon @click="menu_drawer = !menu_drawer">
            <v-icon>mdi-close</v-icon>
          </v-btn>
        </v-col>
      </v-row>
      <v-list>
        <v-list-item color="transparent" link to="/">
          <v-list-item-title class="black--text">Inicio</v-list-item-title>
        </v-list-item>

        <v-list-group no-action color="grey">
          <template v-slot:activator>
            <v-list-item-title class="black--text"
              >Actividades</v-list-item-title
            >
          </template>

          <v-list-item link to="/minicursos">
            <v-list-item-title class="black--text"
              >Minicursos</v-list-item-title
            >
          </v-list-item>
          <v-list-item link to="/ponencias">
            <v-list-item-title class="black--text">Ponencias</v-list-item-title>
          </v-list-item>
        </v-list-group>

        <v-list-group no-action color="grey">
          <template v-slot:activator>
            <v-list-item-title class="black--text">Concursos</v-list-item-title>
          </template>

          <v-list-item link to="/concursos">
            <v-list-item-title class="black--text">
              Concurso de Destreza</v-list-item-title
            >
          </v-list-item>
          <v-list-item link to="/concursos">
            <v-list-item-title class="black--text"
              >Concursos de Investigación</v-list-item-title
            >
          </v-list-item>
        </v-list-group>

        <v-list-item color="white" href="/#colaboradores">
          <v-list-item-title class="black--text"
            >Colaboradores</v-list-item-title
          >
        </v-list-item>
        <v-list-item color="white" to="/embajadores">
          <v-list-item-title class="black--text">Embajadores</v-list-item-title>
        </v-list-item>
        <!-- <v-list-item color="white" to="/">
          <v-list-item-title class="black--text"
            >Meza Redonda</v-list-item-title
          >
        </v-list-item>
        <v-list-item color="white" to="/">
          <v-list-item-title class="black--text">Paneles</v-list-item-title>
        </v-list-item>-->
      </v-list>

      <template v-slot:append>
        <div class="pa-2">
          <v-btn
            href="https://participante.coneimera.org/registro"
            target="_blanck"
            large
            link
            block
            color="primary"
          >
            INSCRIPCIONES
          </v-btn>
        </div>
      </template>
    </v-navigation-drawer>
    <v-main class="main-content">
      <transition name="fade" mode="out-in">
        <router-view />
      </transition>
    </v-main>
    <v-footer id="footer" dark>
      <v-container>
        <div class="titulo-container">



          <div class="separador"></div>
        </div>
        <v-row class="mx-auto w-75" justify="center">
          <v-col cols="6" sm="4" class="mx-auto">
            <v-btn
              link
              href="#"
              block
              color="red"
              large
              >ENVIAME UN MENSAJE</v-btn
            >
          </v-col>
        </v-row>

        <v-divider class="grey darken-2 mb-12 mt-6"></v-divider>

        <v-row justify="space-between">
          <v-col cols="12" sm="6" md="4">
            <v-row>
              <v-col cols="12" md="12">
                <v-img class="mx-auto" v-bind:src="require('../assets/imagenes/logTMC.png')" width="60%" />

              </v-col>
              <v-col cols="12" md="12">
                <p class="text-sm-body-2">
                  Tecnologia en Mega Construccion Integral Sociedad
                  Anonima Cerrada | Tmc Integral Sac.
                  CONTRATISTAS GENERALES
                </p>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="12" sm="6" md="4" class="d-flex justify-center">
            <div class="footer-menu">
              <h4 class="mb-2">Menu</h4>
              <v-list flat dense color="transparent">
                <v-list-item-group no-action sub-group class="">
                  <v-list-item
                    dense
                    v-for="(item, i) in menu_items"
                    :key="i"
                    link
                    :to="item.ruta"
                    class="item-menu"
                  >
                    <v-list-item-content class="py-0">
                      <v-list-item-title
                        v-text="item.nombre"
                      ></v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-list-item-group>
              </v-list>
            </div>
          </v-col>
          <v-col
            cols="12"
            sm="6"
            md="4"
            class="d-flex justify-center justify-md-end"
          >
            <div class="footer-contactos">
              <h4 class="mb-2">Contactos</h4>
              <v-list flat dense color="transparent">
                <v-list-item-group no-action sub-group>
                  <v-list-item
                    dense
                    v-for="(item, i) in contacto_items"
                    :key="i"
                    link
                    :href="item.ruta"
                    target="_black"
                    class="item-menu"
                  >
                    <v-list-item-icon class="mr-2">
                      <v-icon dense v-text="item.icono"></v-icon>
                    </v-list-item-icon>
                    <v-list-item-content class="py-0">
                      <v-list-item-title
                        v-text="item.nombre"
                      ></v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-list-item-group>
              </v-list>
            </div>
          </v-col>
        </v-row>

        <v-divider class="grey darken-2 mb-4 mt-4"></v-divider>

        <v-row class="d-flex justify-end">
          <v-col cols="6" class="text-end grey--text">
            <small> © TMC INTEGRAL SAC - 2021 </small>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",
  metaInfo: {
    title: "CONEIMERA",
    titleTemplate: "%s | CONEIMERA",
  },
  methods: {
    handleScroll: function (evt, el) {
      if (window.scrollY > 2 && window.innerWidth>600) {
        el.setAttribute(
          "style",
          "background:black; border-bottom:solid 5px red; ",
        );
      }
      if (window.scrollY < 1 && window.innerWidth>600) {
        el.setAttribute(
          "style",
          "background:transparent; transition: opacity 0.3s, visibility 0.3s;"
        );
      }
      //return window.scrollY > 100;
    },
  /*   handleScroll2: function (evt, el) {
      if (window.scrollY > 1) {
        el.setAttribute("style", "transition: opacity 2.6s;",);
      }
      if (window.scrollY < 1) {
        el.setAttribute(
          "style",
          "background:transparent; transition: opacity 2.6s; margin-top: 30px; color:white;"
        );
      }
      //return window.scrollY > 100;
    },
    handleScroll3: function (evt, el) {
      if (window.scrollY > 1) {
        el.setAttribute("style", "transition: opacity 1.6s;");
      }
      if (window.scrollY < 1) {
        el.setAttribute("style", "background:transparent; margin-top: 5px;");
      }
      //return window.scrollY > 100;
    },
    handleScroll4: function (evt, el) {
      if (window.scrollY > 1) {
        el.setAttribute("style", "transition: opacity 1.6s;");
      }
      if (window.scrollY < 1) {
        el.setAttribute("style", "background:transparent; margin-top: 20px;");
      }
      //return window.scrollY > 100;
    }, */
  },

  data: () => ({
    menu_drawer: false,
    pos: "uno",

    menu_items: [
      { nombre: "Inicio", ruta: "#", sub_menu: null }, //falta
      { nombre: "Nosotros", ruta: "#" },
      { nombre: "Servicios", ruta: "#" },
      {
        nombre: "Experiencia",
        ruta: "#",
      },
      { nombre: "Representantes", ruta: "#", sub_menu: null },

      //{ nombre: "Meza Redonda", ruta: "/", sub_menu: null },
      //{ nombre: "Paneles", ruta: "/", sub_menu: null },
    ],
    contacto_items: [
      { nombre: "Ilave - Av. el niño 541", ruta: "", icono: "mdi-map-marker" },
      { nombre: "tmc.integral@gmail.com", ruta: "", icono: "mdi-mail" },
      { nombre: "+51 968291919", ruta: "", icono: "mdi-whatsapp" },
      { nombre: "+51 948035990", ruta: "", icono: "mdi-phone" },
      {
        nombre: "Facebook",
        ruta: "https://www.facebook.com/tmcintegral",
        icono: "mdi-facebook",
      },
      {
        nombre: "Instagram",
        ruta: "https://www.facebook.com/tmcintegral",
        icono: "mdi-instagram",
      },
    ],
  }),
};
</script>
<style>
.main-content {
  overflow: hidden;
}
.navbar {
  background: transparent;
  position: fixed;
  max-width: 100vw;
  width: 100%;
  z-index: 1;

}
.navbar .v-list {
  background: transparent;
  color:white;
}

.list-item-content {
  color:white;
}

.navbar .v-list-item:hover,
.navbar a:hover {
  color: #f23a29;
  font-weight: 600;
}
.menu_desplegable {
  z-index: 2;
}
.barrar_menu {
  background: transparent;
  height: 80px;
  width: 100%;
  padding: 0px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  -webkit-box-shadow: 0px 2px 13px -1px rgba(46, 46, 46, 0.56);
  -moz-box-shadow: 0px 2px 13px -1px rgba(46, 46, 46, 0.56);
  box-shadow: 0px 2px 13px -1px rgba(46, 46, 46, 0.56);
}

.imgLogo {
  margin-left:0px;
  height: 60px;
}
.containerbg{
  background:none;
}


@media (max-width: 600px) {

  .barrar_menu {
    background: white;
    height: 50px;
    width: 100%;
    -webkit-box-shadow: 0px 2px 13px -1px rgba(46, 46, 46, 0.56);
    -moz-box-shadow: 0px 2px 13px -1px rgba(46, 46, 46, 0.56);
    box-shadow: 0px 2px 13px -1px rgba(46, 46, 46, 0.56);
  }
  .imgLogo {
    margin-left: 0px;
    height: 50px;

  }
  .containerbg{
    margin:0px;
    padding: 5px;
    background:white;

  }

}
</style>
