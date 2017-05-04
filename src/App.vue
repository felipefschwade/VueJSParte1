<template>
  <div>
    <h1>{{ titulo }}</h1>
    <ul>
      <li v-for="foto of fotos">
        <img :src="foto.url" :alt="foto.titulo">
      </li>
    </ul>
  </div>
</template>

<script>
export default {

 data() {
    return {
      titulo: 'Alurapic',
      fotos: [
        { 
          url: 'http://dicasboaspracachorro.com.br/wp-content/uploads/2014/06/hotel-para-cachorro.jpeg', 
          titulo: 'Cachorro'
        },
        { 
          url: 'http://dicasboaspracachorro.com.br/wp-content/uploads/2014/06/hotel-para-cachorro.jpeg', 
          titulo: 'Cachorro'
        }
      ] 
    }
 }

}
</script>

<style>

</style>
