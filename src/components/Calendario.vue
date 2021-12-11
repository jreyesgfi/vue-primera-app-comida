<template>
    <div class= "calendario">
        <h1 class= "nombre-mes">
            {{mes}}
        </h1>
        <div class = "calendario-container" >
            <div class="dia" v-for="(dia, index) in totalDias" :key=index>
                <strong>{{dia}}</strong>
                <br>
                Vacío
            </div>
        </div>
    </div>
</template>

<script>
    // Tomamos el valor de la pantalla actual de la App.vue
    //import App from './../App.vue'

    // Determinamos en que mes estamos
    const meses = ['enero','febrero','marzo','abril','mayo','junio','julio','agosto','septiembre','octubre','noviembre','diciembre']
    var mesNumerico = new Date(Date.now()).getMonth();
    var mes = meses[mesNumerico]

    // Definimos el número de días que tiene el mes actual
    const meses31 = ['enero', 'marzo', 'mayo', 'julio', 'agosto','octubre','diciembre'];
    var totalDias = 30;
    if (meses31.includes(mes)){
        totalDias = 31;
    }
    else if (mes =='febrero'){
        totalDias = 28;
    }

    export default {
        name: 'Calendario',
        data() {
            return{
                totalDias,
                mes
            }           
        }
    }
</script>

<style>
.calendario{
    width: 80%;
    height:50%;
    left:0;
    right:0;
    margin:auto;
    top: 10vh;
    border: solid 3px grey;
    min-width: 300px;
    max-width: 600px;
    position:relative;
}
.nombre-mes{
    margin: 15px auto;
}
.calendario-container{
    display:flex;
    flex-wrap: wrap;
    position:relative;
    justify-content:safe;
    padding: 2px;
}
.dia{
    background: greenyellow;
    width: calc(100% / 7);
    height: 9vh;
    border: solid 1px black;
    box-sizing:border-box;
}


</style>