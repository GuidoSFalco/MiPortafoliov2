<template>
  <v-app id="app">
    <v-img height="200px" src="./assets/luca-bravo-XJXWbfSo2f0-unsplash.jpg">
    </v-img>
    <v-row no-gutters class="justify-center mt-8">
      <v-col class="mx-4 px-6" cols="2" v-for="design, n in designs" :key="n" style="max-width: 200px;">
        <v-row
          :style="`background-color: #ECEFF1; box-shadow: ${(design.selected) ? 'inset ' : ''} 10px 10px 20px #C2C4C6; height: 3rem; border-radius: 12px; color: ${(design.selected) ? '#A9A9A9' : 'black'}`"
          @click="changeDesign(n)">
          <v-col class="d-flex justify-center align-center">
            <span>{{ design.title }}</span>
          </v-col>
        </v-row>
      </v-col>
    </v-row>

    <v-row class="mx-10" no-gutters>

      <v-col class="d-flex justify-center">
        <v-row style="max-width: max-content; max-height: 240px;">
          <v-col class="d-flex justify-end" cols="8" style="min-width: 800px;">

            <v-card class="d-flex px-8 py-6 tarjetapersonal" width="80%" height="100%" elevation="0"
            style="
            background-color: #E3F2FD;
            border-radius: 40px;
            box-shadow: 40px 40px 80px #C9C4D1, -40px -40px 80px white !important;">
    
              <v-img width="200px" height="100%" src="./assets/foto.png" style="border-radius: 20px;"></v-img>
    
              <span class="mt-12 ml-4">Me presento, soy Guido, aunque quizás ya lo sepas si entraste a esta página desde mi perfil de LinkedIn,
                en caso contrario te invito a que conozcas mi historial profesional, he realizado trabajos como Desarrollador
                FullStack aunque tengo conocimientos mas profundos en el ambiente Frontend.</span>
            </v-card>
          </v-col>

          <v-col cols="4" class="d-flex" style="flex-direction: column; justify-content: space-evenly;">
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
    </v-row>

    <!-- <v-row class="mt-10" no-gutters>
      <v-col>
        <v-row>
          CONOCIMIENTOS EN FRONTEND
        </v-row>
        <v-row>
          <v-card elevation="0" class="conocimientos" 
          style="box-shadow: 20px 20px 40px #b3b3b3, -20px -20px 40px #ffffff !important;">
            <div style="background: transparent; transform: rotateZ(-45deg);">
              grfe
            </div>
          </v-card>
          <v-card elevation="0" class="conocimientos" 
          style="box-shadow: 20px 20px 40px #b3b3b3, -20px -20px 40px #ffffff !important;">
            grfe
          </v-card>
          <v-card elevation="0" class="conocimientos" 
          style="box-shadow: 20px 20px 40px #b3b3b3, -20px -20px 40px #ffffff !important;">
            grfe
          </v-card>
          <v-card elevation="0" class="conocimientos" 
          style="box-shadow: 20px 20px 40px #b3b3b3, -20px -20px 40px #ffffff !important;">
            grfe
          </v-card>
          <v-card elevation="0" class="conocimientos" 
          style="box-shadow: 20px 20px 40px #b3b3b3, -20px -20px 40px #ffffff !important;">
            grfe
          </v-card>
        </v-row>


      </v-col>
      <v-col>
        CONOCIMIENTOS EN BACKEND
      </v-col>
    </v-row> -->

    <v-main>
      <router-view />
    </v-main>
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
      ]
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
  background-color: #66BB6A !important;
  width: 100px;
  height: 100px;
  margin-left: 100px;
  margin-top: 100px;
  transform: rotateZ(45deg);
}
</style>
