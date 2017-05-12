<template>
  <div class="corpo">
    <nav>
      <ul>
        <li v-for="rota of routes">
          <router-link :to="rota.path ? rota.path : '/'">{{ rota.text }}</router-link>
        </li>
      </ul>
    </nav>
    <router-view></router-view>
  </div>
</template>
<script>
  import { routes } from './routes';
  export default {
      data() {
        return {
          routes
        }
      }
  }
</script>
<style scoped>
  .corpo {
    font-family: Helvetica, Sans-serif;
    margin: 0, auto;
    width: 96%;
  }
</style>