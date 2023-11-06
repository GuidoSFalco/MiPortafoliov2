<template>
  <v-app id="app">
    <v-row style="flex-direction: column;" no-gutters>

      <v-img height="400px" src="./assets/luca-bravo-XJXWbfSo2f0-unsplash.jpg">
      </v-img>
      
      <v-col style="margin-top: 40px; margin-bottom: 120px;">
        <v-row class="d-flex justify-center" no-gutters>

          <v-col class="mx-4 px-6" v-for="design, n in designs" :key="n" style="max-width: 200px;">
            <v-card :style="`background-color: #ECEFF1; box-shadow: ${(design.selected) ? 'inset ' : ''} 10px 10px 20px #C2C4C6; height: 3rem; border-radius: 12px; color: ${(design.selected) ? '#A9A9A9' : 'black'}`"
            @click="changeDesign(n)">
            <v-col class="d-flex justify-center align-center">
                <span>{{ design.title }}</span>
              </v-col>
            </v-card>
          </v-col>
        </v-row>
      </v-col>


      <!-- TARJETA PERSONAL + MEDIOS DE COMUNICACION -->
      <v-col class="d-flex justify-center" style="min-height: max-content">
        <v-row no-gutters style="max-width: max-content; max-height: max-content;">

          <!-- TARJETA PERSONAL -->
          <v-col class="d-flex justify-end" cols="8" style="min-width: 800px;">
            <v-card class="d-flex px-8 py-6 tarjetapersonal" width="80%" height="100%" elevation="0"
            style="
            background-color: #E3F2FD;
            border-radius: 40px;
            box-shadow: 40px 40px 80px #C9C4D1, -40px -40px 80px white !important;
            perspective: 1000px;"
            @mousemove="rotateCard" @mouseleave="resetCard">
    
              <v-img width="200px" height="100%" src="./assets/foto.png" style="border-radius: 20px;"></v-img>
    
              <span class="mt-12 ml-4">Me presento, soy Guido, aunque quizás ya lo sepas si entraste a esta página desde mi perfil de LinkedIn,
                en caso contrario te invito a que conozcas mi historial profesional, he realizado trabajos como Desarrollador
                FullStack aunque tengo conocimientos mas profundos en el ambiente Frontend.</span>
            </v-card>
          </v-col>

          <!-- MEDIOS DE COMUNICACION -->
          <v-col cols="4" class="pl-8 d-flex" style="flex-direction: column; justify-content: space-evenly;">
            <v-btn class="redes redes-whatsapp d-flex justify-start" icon tile width="50px" height="50px" style="overflow: hidden;">
              <v-icon style="font-size: 2rem; margin-left: 13px;">mdi-whatsapp</v-icon>
              <span class="ml-4">Whatsapp</span>
            </v-btn>
            <v-btn class="redes redes-linkedin d-flex justify-start" icon tile width="50px" height="50px" style="overflow: hidden;">
              <v-icon style="font-size: 2rem; margin-left: 13px;">mdi-linkedin</v-icon>
              <span class="ml-4">LinkedIn</span>
            </v-btn>
            <v-btn class="redes redes-cv d-flex justify-start" icon tile width="50px" height="50px" style="overflow: hidden;">
              <v-icon style="font-size: 2rem; margin-left: 13px;">mdi-folder-arrow-down</v-icon>
              <span class="ml-4">Descargar CV</span>
            </v-btn>
          </v-col>

  
  
        </v-row>
      </v-col>

      <!-- CONOCIMIENTOS FRONTEND Y BACKEND -->
      <v-col style="margin-top: 200px">

        <v-row no-gutters>
          <!-- TITULO FRONTEND -->
          <v-col cols="6" class="d-flex">
            <span class="mx-auto">CONOCIMIENTOS EN FRONTEND</span>
          </v-col>

          <!-- TITULO BACKEND -->
          <v-col cols="6" class="d-flex">
            <span class="mx-auto">CONOCIMIENTOS EN BACKEND</span>
          </v-col>
        </v-row>

        <v-row no-gutters>

          <!-- CONOCIMIENTOS FRONTEND 1 RENGLON-->
          <v-col cols="6">
            <v-row no-gutters style="padding-inline: 100px; justify-content: space-evenly;">

              <v-card class="conocimientos" elevation="0" @click="openModalLenguaje"  style="background-color: transparent;">
                <v-img class="mt-4" width="125px" min-width="125px" src="./assets/vue-js-logo.png"></v-img>
              </v-card>

              <v-card class="conocimientos" elevation="0" @click="openModalLenguaje"  style="background-color: transparent;">
                  <v-img class="mt-4" width="100px" min-width="100px" src="./assets/html5-logo.png"></v-img>
              </v-card>
              
              <v-card class="conocimientos" elevation="0" @click="openModalLenguaje"  style="background-color: transparent;">
                  <v-img class="mt-4" width="125px" min-width="125px" src="./assets/angular-logo.png"></v-img>
              </v-card>
            </v-row>
          </v-col>

          <!-- CONOCIMIENTOS BACKEND 1 RENGLON -->
          <v-col cols="6">
            <v-row no-gutters style="padding-inline: 100px; justify-content: space-evenly;">
              
              <v-card class="conocimientos" elevation="0" @click="openModalLenguaje"  style="background-color: transparent;">
                  <v-img class="mt-4" width="125px" min-width="125px" src="./assets/netcore-logo.png"></v-img>
              </v-card>
            </v-row>
          </v-col>
        </v-row>

        <v-row no-gutters>

          <!-- CONOCIMIENTOS FRONTEND 2 RENGLON -->
          <v-col cols="6">
            <v-row style="justify-content: space-evenly;" no-gutters>

              <v-card style="background-color: transparent;" class="mt-10 conocimientos" elevation="0" @click="openModalLenguaje">
                  <v-img width="100px" src="./assets/JavaScript-logo.png"></v-img>
              </v-card>

              <v-card style="background-color: transparent;" class="mt-5 conocimientos" elevation="0" @click="openModalLenguaje">
                  <v-img width="125px" src="./assets/css-logo.png"></v-img>
              </v-card>

              <v-card style="background-color: transparent;" class="mt-10 conocimientos" elevation="0" @click="openModalLenguaje">
                  <v-img width="100px" src="./assets/typescript-logo.png"></v-img>
              </v-card>

              <v-card style="background-color: transparent;" class="mt-10 conocimientos" elevation="0" @click="openModalLenguaje">
                  <v-img width="100px" src="./assets/bootstrap-logo.png"></v-img>
              </v-card>

            </v-row>
          </v-col>

          <!-- CONOCIMIENTOS BACKEND 2 RENGLON -->
          <v-col cols="6" style="padding-inline: 120px">
            <v-row no-gutters style="padding-inline: 100px; justify-content: space-evenly;">
              <v-card style="background-color: transparent;" class="mt-10 conocimientos" elevation="0" @click="openModalLenguaje">
                  <v-img width="100px" src="./assets/sql-logo.png"></v-img>
              </v-card>

              <v-card style="background-color: transparent;" class="mt-5 conocimientos" elevation="0" @click="openModalLenguaje">
                  <v-img width="100px" src="./assets/c-sharp-logo.png"></v-img>
              </v-card>
              
            </v-row>
          </v-col>
        </v-row>
      </v-col>

      <v-col style="margin-top: 200px;">
        <v-row style="justify-content: space-evenly;">
          <v-img max-width="300px" src="./assets/igor-omilaev-W7wbDcPx6lw-unsplash.jpg"
          style="
          border-radius: 30px;
          box-shadow: 20px 20px 40px #C9C4D1, -20px -20px 40px #801414;"></v-img>
          <v-img max-width="300px" src="./assets/esmihel-muhammad-GQROYIBu5r0-unsplash.jpg"
          style="
          border-radius: 30px;
          box-shadow: 20px 20px 40px #A5A7A9, -20px -20px 40px #ffffff;"></v-img>
        </v-row>
      </v-col>

      <v-col style="margin-top: 200px">
        <span style="margin-left: 100px; color: #A6A6A6; font-size: 30px;">... A CONTINUACION ALGUNOS DE MIS PROYECTOS REALIZADOS</span>
      </v-col>

      <v-col style="margin-top: 200px">
        <v-row no-gutters style="justify-content: space-evenly;">
          <v-card elevation="0" width="400px" height="250px" style="
          overflow: hidden;
          border-radius: 40px;
          box-shadow: 30px 30px 60px #C9C4D1, -30px -30px 60px #ffffff !important;">
            <v-img src="./assets/esmihel-muhammad-GQROYIBu5r0-unsplash.jpg">

              <p class="ml-10 mt-5">IR A <span style="color: #906CAD">YO JUST LEARN</span>
                <v-icon>
                  mdi-arrow-right
                </v-icon>
              </p>
            </v-img>
          </v-card>
        </v-row>
      </v-col>
      
      <v-col style="margin-top: 200px">
        <v-row no-gutters style="justify-content: space-evenly;">
          
        </v-row>
      </v-col>
    
    </v-row>

    <v-main>
      <router-view />
    </v-main>


    <v-dialog
    v-model="model"
        transition="dialog-bottom-transition"
        max-width="600"
      >
        <template>
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Opening from the bottom</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12">Hello world!</div>
            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="model = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => {
    return {
      designs: [
        { title: 'Diseño 1', selected: true },
        { title: 'Diseño 2', selected: false },
      ],

      model: false,
    }
  },
  methods: {
    changeDesign(index) {
      this.designs = this.designs.map((item) => {
        item.selected = false
        return item
      })

      this.designs[index].selected = true
    },

    openModalLenguaje() {
      this.model = true
    },

    rotateCard(event) {
      const card = event.currentTarget;
      const cardRect = card.getBoundingClientRect();
      const cardCenterX = cardRect.left + cardRect.width / 2;
      const cardCenterY = cardRect.top + cardRect.height / 2;
      const angleX = (event.clientY - cardCenterY) / 10;
      let angleY = (event.clientX - cardCenterX) / 10;
      card.style.transform = `rotateX(${angleX}deg) rotateY(${angleY}deg)`;

      console.log(event)
    },

    resetCard(event) {
      const card = event.currentTarget;
      card.style.transform = 'none';
    }
  }
};
</script>

<style scoped>
#app {
  background-color: #EDE7F6;
  height: max-content;
}


.redes {
  border-radius: 10px;
  box-shadow: 20px 20px 40px #BEB9C5,
              -20px -20px 40px white !important;
  transition: all .5s ease;
}

.redes:hover {
  width: 220px !important;
}

.redes-whatsapp:hover {
  color: green !important;
}
.redes-linkedin:hover {
  color: #2196F3 !important;
}
.redes-cv:hover {
  color: #673AB7 !important;
}

.conocimientos {
  transition: all .3s ease;
}
.conocimientos:hover {
  transform: translateY(10px);
}
/* .conocimientos {
  background-color: #66BB6A !important;
  width: 100px;
  height: 100px;
  margin-top: 100px;
  border-radius: 10px !important;
  transform: rotateZ(45deg);
} */



</style>
