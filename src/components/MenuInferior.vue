<template>
    <div class= "navbar-container">
        <div class= "navbar-content">
            <router-link to ="/">
                <i class='bx bx-code-alt bx-sm'></i>
            </router-link>
            <router-link to ="/codigo">
                <i class='bx bx-code-alt bx-sm'></i>
            </router-link>
            <router-link to ="/aboutme">
                <i class='bx bx-code-alt bx-sm'></i>
            </router-link>
            <router-link to ="/proyects">
                <i class='bx bx-code-alt bx-sm'></i>
            </router-link>
        </div>
    </div>
</template>

<script>
export default {
    // Estoy creando la parte del sccript de la clase
    // Arriba he creado lo equivalente al refresh
    name: 'MenuInferior'
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