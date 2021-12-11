<template>
  <div class='menu-inferior'>
    <MenuInferior>
    </MenuInferior>
    <Calendario v-show='pantallaActual == "calendario"'>
    </Calendario>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
import Calendario from './components/Calendario.vue';
import MenuInferior from './components/MenuInferior.vue';

// actualizar la pantalla actual
var pantallaActual = ref('calendario')
const cambiarPantalla = (pantalla) =>{
  console.log(pantallaActual.value)
  pantallaActual.value = pantalla
  console.log(pantallaActual.value)
}
  export default {
    name: 'App',
    components: {
      MenuInferior,
      Calendario
    },
    data(){
      return {
        mensaje: "mensaje de prueba",
        pantallaActual,
        cambiarPantalla
      }
    },
    methods: {
      comprobarSiFunciona(pantalla) {
        return this.mensaje + pantalla;
      },
    },
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
