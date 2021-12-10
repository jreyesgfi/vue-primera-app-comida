<template>
  <div class='menu-inferior'>
    <MenuInferior>
    </MenuInferior>
    <Calendario>
    </Calendario>
  </div>
</template>

<script>
import Calendario from './components/Calendario.vue';
import MenuInferior from './components/MenuInferior.vue';
  export default {
    name: 'App',
    components: {
      MenuInferior,
      Calendario
    },
    data(){
      return {
        mensaje: "mensaje de prueba",
        pantallaActual: 'pantallaMes'
      }
    }
  }

</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
*{
  margin: 0px;
  padding: 0px;
}
</style>
