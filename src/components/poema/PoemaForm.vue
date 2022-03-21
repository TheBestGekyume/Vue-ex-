<template>
<section class="container">
    <form class="container mt-4 fs-form" onchange="poemaController.validRequired()">
        

        <div class= "cabin-font bg-purple-2 preto p-4 mt-5 rounded-3">
            <div class="form-group mb-3">
                <label for="name" class="form-label">Nome do Poema</label>
                <input type="text" class="form-control required" id="title" name="title" 
                placeholder="Digite o título do poema" v-model="poema.title">
                <span class="textErro">digite o título do poema.</span>
            </div>

            <div class="form-group mb-3">
                <label for="image" class="form-label">Imagem do Poema</label>
                <input type="file" class="form-control required" id="image" name="image" >
                <span class="textErro">insira uma imagem para representar o poema.</span>
            </div>

            <div class="form-group mb-3">
                <label for="date" class="form-label">Data</label>
                <input type="date" class="form-control required" id="date" name="date" 
                placeholder="dd/mm/aaaa" v-model="poema.date">
                <span class="textErro">insira a data que o poema foi criado.</span>
            </div>

           <div class="form-group mb-3" >
              <label for="text" class="form-label">Poema</label>
              <textarea type="text" class="form-control required" id="textP" name="text" rows="10" 
              placeholder="Escreva o Poema aqui" v-model="poema.textp"> </textarea>
              <span class="textErro">escreva o conteudo do poema.</span>
          </div>

            <div class="mt-5">
                <button id="button_save" type="button" class="button btn btn-dark btn-lg px-5" 
                 @click="addPoema()">Salvar</button>
               <button id="button_cancel" type="button" class="button btn btn-dark btn-lg px-5 mx-3" 
               >Cancelar</button>
           </div>
           </div> 
     </form>
     {{poema}}
</section>
</template>

<script>
import Poema from "./Poema";
let poema = new Poema();
export default {
    name:"PoemaFormComponent",
    components: {
    ProdutoListComponent,
  },
    data(){
        return{
            poema
        };
    },
    methods: {
    addPoema() {
      try {
        poema.add();
        alert("Poema Cadatrado!");
      } catch (ex) {
        alert(ex);
      }
    },
  },
};

</script>

<style scoped>
/* fonts link */
@import url('https://fonts.googleapis.com/css2?family=Cabin&display=swap');

table, th ,td{
    border:solid 2px #c8d14d !important;
    color: #dfdfdf;
}

th{
    color: #eeff00 !important;
}

i{
    color: #fbff00af;
}

i:hover{
    color: #fbff00ea;
}

input, textarea{
    background: linear-gradient(#111111,#353535) !important;

    border: #242424 !important;
    color: #ffffff !important;
}

.textErro{
    display: none;
    color: #920000;
    font-weight: bold;
    font-size: 20px;
}

/* CLASS */

.button:hover{
    border-bottom:solid 1px #1a1a1a !important;
}

button{
    border-bottom:solid 5px #1a1a1a  !important;
}

.fs-form{
    font-size:26px;
}

/* MOBILE */

@media screen and (max-width:991px){

    #button_dell , #button_save, #button_list{
        margin:10px 40px 10px 20px !important;
        padding: 10px 15px !important;

    }

    .navbar-dark .navbar-toggler {
        color: #1a1524;
        border:#1a1524;
    }

    .navbar-dark .navbar-toggler:hover {
        color: #b638ff;
        border:#b638ff;
    }
}
</style>