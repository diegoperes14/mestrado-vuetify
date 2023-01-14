<template>
  <v-container>
    <v-row class="text-center">

      <v-col class="mb-4">
        <h2 class="display-2 font-weight-bold mb-3">
          IWIM
        </h2>

        <p class="subheading font-weight-regular">
          Interface Web para Identificação de Melanoma
        </p>
      </v-col>

      <v-col cols="12">
        <v-img
            :src="require('@/assets/IWIM_coracao.png')"
            class="mx-auto"
            contain
            width="200"
        />
      </v-col>
      <v-col cols="12">
        <v-btn
            block
            elevation="2"
            color="primary"
            @click="abrirJanelaVerificacao"
        >VERIFICAR UMA IMAGEM</v-btn>
      </v-col>

      <v-col cols="12">
        <v-btn
            block
            elevation="2"
            color="primary"
            @click="abrirJanelaSubimissao"
        >SUBMETER UMA IMAGEM</v-btn>
      </v-col>
    </v-row>
  <JanelaVerificacao
    ref="JanelaVerificacao"
  ></JanelaVerificacao>
  <JanelaSubimissao
    ref="JanelaSubimissao"
  ></JanelaSubimissao>
  </v-container>
</template>

<script>
  import JanelaVerificacao from '@/components/JanelaVerificacao.vue';
  import JanelaSubimissao from '@/components/JanelaSubimissao.vue';
  export default {
    name: 'PaginaPrincipal',
    components:{
      JanelaVerificacao,
      JanelaSubimissao
    },
    data: () => ({

    }),
    methods:{
      abrirJanelaVerificacao(){
        this.$refs.JanelaVerificacao.dialog = true;
        console.log("Abrir Janela Verificacao");
      },
      abrirJanelaSubimissao(){
        this.$refs.JanelaSubimissao.dialog = true;
        console.log("Abrir Janela Submissao");
      },

    }
  }
</script>
