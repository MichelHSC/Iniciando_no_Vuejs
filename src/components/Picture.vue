<template>
    <div>
        <img :src="avatar" :alt="descricao">
        <MudarImagem @mudar-imagem="trocarImagem"/>
    </div>
</template>

<script>
import MudarImagem from './MudarImagem.vue'


export default{
    name: 'Picture',
    components:{
        MudarImagem
    },
    data(){
        return{
            avatar: "/img/avatar.png",
            descricao: 'Michel Henrique'
        }
    },
    methods:{
        trocarImagem(){
            // this.avatar = "/img/avatar2.png"
            if(this.avatar === "/img/avatar.png"){
                this.avatar= "/img/avatar2.png"
            }else{
                this.avatar= "/img/avatar.png"
            }
    }
}
}
</script>