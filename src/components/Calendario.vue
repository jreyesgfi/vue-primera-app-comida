<template>
    <div class= "calendario">
        <h1 class= "nombre-mes">
            {{mes}}
        </h1>
        <div class = "calendario-container">
            <Dia
                v-for="(dia, index) in listaDias"
                :key=index
                :numero="dia.num"
                :todos="dia.todos"
                :hueco="dia.hueco"
                :posicion=index>
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

    // Empezamos por los huecos iniciales (de momento serán fijos, no dependen del mes)
    const huecosIniciales = 3;
    var listaDias = [];
    for (let num=1; num <= huecosIniciales; num++){
        const dia = {num:num, todos:[],hueco:true};
        listaDias.push(dia);
    }

    // Ahora creamos el resto de días como diccionarios que recorrera el v-for
    for (let num=1; num <= totalDias; num++){

        const dia = {num:num, todos:['Hola'],hueco:false};
        listaDias.push(dia);
    }

    export default {
        name: 'Calendario',
        components:{
            Dia
        },
        data() {
            return{
                mes,
                listaDias
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