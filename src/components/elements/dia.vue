<template>
    <div :class="{ finde: finDeSemana }" class="dia entrada-calendario" v-if="visible">
        <strong>{{num}}</strong>
        <br>
        <p v-for="(todo,index) in listaTodos"
        :key = "index">
            {{todo}}
        </p>
    </div>
    <div class="entrada-calendario" v-else>

    </div>
</template>

<script>
    //import { ref } from '@vue/reactivity';
    // Esto es equivalente a un método estático y nos está alterando todo el calendario
    // var finDeSemana = ref(false);
    // const cambiarFinDe = (value) =>{
    //    finDeSemana.value = value
    // }
    export default {
        name: 'Dia',
        props: {
            numero: Number,
            posicion:Number,
            todos:String,
            hueco:Boolean,
            finde:{
                type:Boolean,
                default() {
                    return false
                }
            }
        },
        data(){
                return{
                    num:this.numero,
                    pos:this.posicion,
                    listaTodos:this.todos,
                    visible:!this.hueco,
                    finDeSemana:this.finde
                }
        }
    }
    
</script>
        
<style scoped>
    .entrada-calendario{
    width: calc(100% / 7);
    height: 9vh;
    border: solid 1px black;
    box-sizing:border-box;
    }
    .dia{
        background: greenyellow;
    }
    .finde{
        background:red;
    }
</style>