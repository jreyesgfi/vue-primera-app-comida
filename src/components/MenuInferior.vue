<template>
    <div class= "navbar-container">
        <div class= "navbar-content">
            <div class= "boton-nav">
                <i @click="cambiarPantalla('principal')" class='bx bxs-home'></i>
            </div>
            <div class= "boton-nav">
                <i @click="cambiarPantalla('calendario')" class='bx bxs-calendar'></i>
            </div>
            <div class= "boton-nav">
                <i @click="cambiarPantalla('codigo')" class='bx bx-code-alt bx-sm'></i>
            </div>
            <div class= "boton-nav">
                <i @click="cambiarPantalla('comentarios')" class='bx bx-message-square-dots'></i>
            </div>
        </div>
    </div>
</template>

<script>
import App from './../App.vue'
export default {
    // Estoy creando la parte del sccript de la clase
    // Arriba he creado lo equivalente al refresh
    name: 'MenuInferior',
    methods:{
        cambiarPantalla : function(pantalla) {
            return App.data().cambiarPantalla(pantalla)
        }
    }
}
</script>

<style>
.navbar-container{
    width: 100%;
    margin:0px;
    position: fixed;
    bottom: 0;
}
.navbar-content{
    padding:10px min(15vw,40px);
    display: flex;
    box-sizing: border-box;
    max-width: 500px;
    justify-content: space-between;
}

a {
    margin:3px;  
}



</style>