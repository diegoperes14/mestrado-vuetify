<template>
    <form ref="formulario">
      <v-row justify="center">
        <v-dialog
          v-model="dialog"
          persistent
          max-width="450"
        >
          <v-card :loading="carregando">
            <v-card-title class="text-h5">
              Resultados
            </v-card-title>
            <v-card-text>

              <v-row>
                <v-col cols="12">
                    <h3>Contorno</h3>
                    <v-img
                        :src="require('@/assets/resultados-placeholders/Contorno.jpg')"
                        class="mx-auto"
                        contain
                        width="250"
                    />
                    <p class="text-justify">
                        {{texto_bordas}}
                    </p>
                </v-col>
            </v-row>

            <v-row>
                <v-col cols="12">
                    <h3>Medidas</h3>
                    <v-img
                        :src="require('@/assets/resultados-placeholders/Medidas.jpg')"
                        class="mx-auto"
                        contain
                        width="250"
                    />
                    <p class="text-justify">
                        {{texto_assimetria}}
                    </p>
                </v-col>
            </v-row>

            <v-row>
                <v-col cols="12">
                    <h3>Resultado Final</h3>
                    <v-img
                        :src="require('@/assets/resultados-placeholders/Resultado.jpg')"
                        class="mx-auto"
                        contain
                        width="250"
                    />
                    <p class="text-justify">
                        {{texto_cores}}
                    </p>
                </v-col>
            </v-row>

            <v-row>
                <v-col cols="12">
                    <h3>Diagnóstico</h3>
                    <p class="text-justify">
                        {{texto_diagnóstico}}
                    </p>
                </v-col>
            </v-row>




  
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn
                color="green darken-1"
                text
                :loading="carregando"
                @click="dialog = false"
              >
                Sair
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-row>
      </form>
    </template>
  
    <script>
    export default {
      name:"JanelaResultados",
      data () {
        return {
          dialog: false,
          carregando: false,
          texto_bordas: 'A lesão segmentada apresenta bordas relativamente regulares, não fugindo do padão visto em histogramas de lesões benignas, espalhando-se pouco além das fronteiras atuais.',
          texto_cores: ' O número de cores identificadas na lesão foi de aproximadamente 10 mil, o que corresponde a um número alto de cores para uma lesão de pele. Isso significa que é possível que a lesão evolua para algo sério, portanto é importante tomar cuidado quando a evolução.',
          texto_assimetria: 'Lesão de Aparência simétrica, indicando uma evolução homogênea de suas bordas até o presente momento.',
          texto_diagnóstico: 'Conforme os dados obtidos a partir treinamento de aprendizado de máquina, é calculado uma probabilidade de 34% de esta lesão ser do tipo maligna, portanto, recomenda-se a procura por um especialista em dermatologia para acompanhar a evolução desta lesão e o devido tratamento caso necessáro.',
        }
      },
      methods:{

      }
    }
  </script>