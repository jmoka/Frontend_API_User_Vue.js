<template>
  <v-app>
    <v-toolbar app color="blue" dark>
      <v-toolbar-title class="headline text-uppercase">
        <span>GraphQL</span>
        <span class="font-weight-light red--text">Client</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <Conteudo />
    </v-content>
  </v-app>
</template>

<script>
import { mapActions } from 'vuex'
import Conteudo from './componentes/Conteudo'

export default {
  name: 'App',
  components: { Conteudo },
  methods: mapActions(['setUsuario']),
  mounted() {
    // Limpar o localStorage quando a página for carregada
    localStorage.removeItem('token');
    this.setUsuario(null)
  }
}
</script>
