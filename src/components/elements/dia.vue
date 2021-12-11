<template>
    <div class="dia">
        <strong>{{num}}</strong>
        <br>
        <p v-for="(todo,index) in listaTodos"
        :key = "index">
            {{todo}}
        </p>
    </div>
</template>

<script>

    export default {
        name: 'Dia',
        props: {
            numero: Number,
            todos:String
        },
        data(){
                return{
                    num:this.numero,
                    listaTodos:this.todos
                }
        }  
    }
</script>
        
<style scoped>
    .dia{
    background: greenyellow;
    width: calc(100% / 7);
    height: 9vh;
    border: solid 1px black;
    box-sizing:border-box;
    }
</style>