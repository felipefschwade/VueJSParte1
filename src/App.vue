
<template>

  <div class="corpo">
    <h1 class="centralizado">{{ titulo }}</h1>
    <ul class="lista-fotos">
      <li v-for="foto of fotos" class="lista-fotos-item">
        <meu-painel :titulo="foto.titulo">
          <img slot="imagem" class="imagem-responsiva" :src="foto.url" :alt="foto.titulo">
        </meu-painel>
      </li>
    </ul>
  </div>

</template>

<script>
import Painel from './components/shared/painel-component/Painel.vue';

export default {

components: {
  'meu-painel' : Painel
},

 data() {
    return {
      titulo: 'Alurapic',
      fotos: [] 
    }
 },

 created() {
   this.$http.get("http://localhost:3000/v1/fotos")
      .then(res => res.json())
      .then(fotos => this.fotos = fotos, err => console.log(err));
 }

}
</script>

<style scoped>
  .centralizado {
    text-align: center;
  }
  .corpo {
    font-family: Helvetica, Sans-serif;
    margin: 0, auto;
    width: 96%;
  }
  .lista-fotos {
    list-style: none;
  }

  .lista-fotos .lista-fotos-item {
    display: inline-block;
  }

  .imagem-responsiva {
    width: 90%;
  }

</style>
