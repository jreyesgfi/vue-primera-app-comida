<template>
    <div class= "calendario" v-if='pantallaMes'>
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
    // Aquí deberíamos preguntarle a App.vue
    import App from './../App.vue'
    var pantallaMes = ()=>{
        return (App.data().pantallaActual == 'pantallaMes');}

    const meses = ['enero','febrero','marzo','abril','mayo','junio','julio','agosto','septiembre','octubre','noviembre','diciembre']
    var mesNumerico = new Date(Date.now()).getMonth();
    var mes = meses[mesNumerico]
    console.log(mes)
    
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
                pantallaMes: pantallaMes(),
                totalDias: totalDias,
                mes: mes
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