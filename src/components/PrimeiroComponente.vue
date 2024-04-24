<template>
    <div>
        <H1>Olá Vue!</H1>
        <p>Meu nome é {{ nome }} tenho {{ age }} anos, trabalho como {{ profissao }}</p>
        <MultiplosEventos/>
        <Reutilizacao/>
        <Reutilizacao/>
        
    </div>
</template>

<script>
    import MultiplosEventos from './MultiplosEventos.vue'
    import Reutilizacao from './Reutilizacao.vue'

    export default{
        name: 'PrimeiroComponente',
        components:{
            MultiplosEventos,
            Reutilizacao
        },
        data(){
            return{
                nome: 'Michel',
                age: 24,
                profissao: 'Programador'
            }
        }
    }
</script>