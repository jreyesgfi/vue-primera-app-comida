<template>
    <div class= "calendario">
        <div class = "calendario-container" v-if="pantallaMes">
            <div class="dia" v-for="(dia, index) in totalDias" :key=index>
                <strong>{{dia}}</strong>
                <br>
                Vacío
            </div>
        </div>
    </div>
</template>

<script>
    var mes = 'marzo';
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
                pantallaMes: true,
                totalDias: totalDias
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