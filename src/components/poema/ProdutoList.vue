<template>
    <table class='table'> 
        <tr> 
            <th>Título</th> 
            <th>Imagem</th> 
            <th>Data</th> 
            <th style= width:50%>Texto</th>
            <td><i class='bi bi-pencil-fill'></i>
             </td> <td><i class='bi bi-trash3-fill'>
                 </i>
            </td>
        </tr>"

        <tr v-for="produto in produtos" :key="produto.id"> 
            <td> {{poemas.title}} </td> 
            <td> {{poemas.image}} </td>
            <td> {{poemas.date }} </td>
            <td> {{poemas.textp}} </td> 
            <td @click="getPoema(this)"> 
                <a href="#"> <i class="bi bi-pencil-fill"></i> </a>
            </td> 
            <td @click="deletePoema(this)"><a href="#listaPoemas">
                <i class="bi bi-trash3-fill"></i></a></td> 
        </tr>
    </table>;
</template>

<script>
import Poema from "./Poema"; //importa a classe Poema do Poema.js
let poema = new Poema(); //cria um Poema com os atributos da classe Poema
export default {
data(){
    return {
        poemas:poema.getAll(), //pega todos os poemas do armazenamento e coloca em poemas[array]
        poema,
    };
},

methods: {
    getPoema(poema) {
      console.log(poema);
      this.poema = poema;
    },
}

}
</script>

<style>

</style>