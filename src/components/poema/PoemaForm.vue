<template>
<section class="container">
    <form class="container mt-4 fs-form" onchange="poemaController.validRequired()">
        <div class= "cabin-font bg-purple-2 preto p-4 mt-5 rounded-3">
            <div class="form-group mb-3">
                <label for="name" class="form-label">Nome do Poema</label>
                <input type="text" class="form-control required" id="title" name="title" placeholder="Digite o título do poema">
                <span class="textErro">digite o título do poema.</span>
            </div>

            <div class="form-group mb-3">
                <label for="image" class="form-label">Imagem do Poema</label>
                <input type="file" class="form-control required" id="image" name="image" placeholder="">
                <span class="textErro">insira uma imagem para representar o poema.</span>
            </div>

            <div class="form-group mb-3">
                <label for="date" class="form-label">Data</label>
                <input type="date" class="form-control required" id="date" name="date" placeholder="dd/mm/aaaa">
                <span class="textErro">insira a data que o poema foi criado.</span>
            </div>

           <div class="form-group mb-3" >
              <label for="text" class="form-label">Poema</label>
              <textarea type="text" class="form-control required" id="textP" name="text" rows="10" placeholder="Escreva o Poema aqui"> </textarea>
              <span class="textErro">escreva o conteudo do poema.</span>
          </div>

            <div class="mt-5">
                <button id="button_save" type="button" class="button btn btn-dark btn-lg px-5" onclick="poemaController.addPoema()">Salvar</button>
               <button id="button_cancel" type="button" class="button btn btn-dark btn-lg px-5 mx-3" onclick="poemaController.excluir()">Cancelar</button>
               <button id="button_list" type="button" class="button btn btn-dark btn-lg px-5 mx-3" onclick="poemaController.getAllPoema()">Listar Poemas</button>
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
    data(){
        return{
            poema
        }
    }
}
</script>

<style scoped>
.textErro{
    display: none;
    color: #920000;
    font-weight: bold;
    font-size: 20px;
}
</style>