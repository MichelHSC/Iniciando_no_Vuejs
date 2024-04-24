<template>
    <div>
        <h2>Meu Formulário</h2>
        <form action="" @submit="enviarFormulario">

            <input type="text" v-model="name">

            <input type="text" v-model="email">
            
            <!-- <div>
                <InputText/>
            </div>
            <div>
                <InputText/>
            </div>
        -->
            <div>
                <Submit/>
            </div> 
        </form>


        <p>Conteúdo</p>
        <p>Conteúdo</p>
        <p>Conteúdo</p>
    </div>
</template>

<script>
import InputText from './Form/InputText.vue'
import Submit from './Form/Submit.vue'

export default{
    name: 'Form',
    components:{
        InputText,
        Submit
    },
    data(){
        return{
            name:'',
            email:'',
        }
    },
    methods: {
        enviarFormulario(e){

        e.preventDefault();

        const name = this.name;
        const email = this.email

        console.log("Formulário Enviado");
        console.log(name);
        console.log(email);
        }
    }
}

</script>


<style scoped>
p{
    margin: 150px;
}
</style>