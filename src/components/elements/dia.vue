<template>
    <div class="dia">
        <strong>{{numero}}</strong>
        <br>
        <p v-for="(todo,index) in todos"
        :key = "index">
            todo
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
                    numero:this.numero,
                    todos:this.todos
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