<template>
    <div class= "calendario">
        <div class = "calendario-container">
            <div class="dia" v-for="(dia, index) in 31" :key=index>
                {{dia}}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Calendario'
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