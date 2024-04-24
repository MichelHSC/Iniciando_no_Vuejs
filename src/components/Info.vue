<template>
    <div>
        <p>{{ email }}</p>

        <button @click="showPorti">{{ textoBotao2 }}</button>

        <p v-if="esta_trabalhando"> Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades</p>
        <p v-show="linguagens">Utilizo as seguintes tecnologias:</p>

        <ul v-if="linguagens">
            <li v-for="(technology, index) in backend_technologies" v-bind:key="index">{{ technology }}</li>
        </ul>
        <p>CEP</p>
        <ul>
            <li v-for="ruas in ceps" :key="ruas.id">
            {{ ruas.log}}
        </li>
        </ul>
        <div>
            <button @click="showEmail">{{textoBotao}}</button>
        </div>

        <p v-show="mostrar_email">Mande uma E-Mail para {{ email }}</p>

        <p>Para acessar meu portifolio <a v-bind:href="Meu_Link" target="_blank">clique aqui </a></p>

        <Picture/>

    </div>
</template>

<script>
import Picture from './Picture.vue'

export default{
    name: 'Info',
    components:{
        Picture
    },
    props:{
        email: String,
        esta_trabalhando: Boolean,
    },
    data(){
        return{
            linguagens: false,
            mostrar_email: false,
            Meu_Link: 'https://www.google.com',
            textoBotao: 'Mostrar E-mail',
            textoBotao2: 'Mostra Portifolio',
            backend_technologies: ['Vue','Css','Python','Angular','HTML','JAVASCRIPT','JAVA'],
            ceps:[
                {id:  1, log: 'Avenida'},
                {id:  2, log: 'Rua'},
                {id:  3, log: 'Travessa'},
                {id:  4, log: 'Viela'}
        ]
        }
    },
    
    methods:{
        showEmail(){
            this.mostrar_email = !this.mostrar_email

            if(!this.mostrar_email){
                this.textoBotao = 'Mostrar E-mail'
            }else{
                this.textoBotao ='Esconder E-mail'
            }
            
        },
        showPorti(){
            this.linguagens = !this.linguagens
            if(!this.linguagens){
                this.textoBotao2 = 'Mostra Portifolio'
            }else{
                this.textoBotao2 ='Esconder Portifolio'
            }
            
        }
    }
}
</script>