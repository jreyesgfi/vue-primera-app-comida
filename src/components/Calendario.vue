<template>
    <div class= "calendario">
        <h1 class= "nombre-mes">
            {{mes}}
        </h1>
        <div class = "calendario-container" >
            <Dia
                v-for="(dia, index) in listaDias"
                :key=index
                :numero = "dia.num"
                :todos = "dia.todos">
            </Dia>
        </div>
    </div>
</template>

<script>

    //  Vamos a definir la clase día
    import Dia from './elements/dia.vue'


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


    // Creamos nuestra lista de dias
    var listaDias = []
    for (let num in totalDias){
        const dia = {num:num, todos:['Hola']}
        listaDias.push(dia)
    }

    export default {
        name: 'Calendario',
        components:{
            Dia
        },
        data() {
            return{
                listaDias,
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


</style>