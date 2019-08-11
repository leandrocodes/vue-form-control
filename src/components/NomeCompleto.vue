<template>
    <div class="nome-completo">
    
        <rotulo nome='Nome'>
            <input type="text" v-model="usuario.nome">
        </rotulo>

        <rotulo nome='Senha'> 
            <input type="password" v-model="usuario.senha">
        </rotulo>
        
    </div>
</template>

<script>
import rotulo from './Rotulo'
export default {
    components:{
        rotulo
    },
    data(){
        return{
            usuario:{
                nome: '',
                sobrenome: ''
            }
        }
    }
}
</script>

<style>

</style>