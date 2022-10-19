<template>
  <section class="container">
        <div v-for="produto in produtos" :key="produto.id">
            <h2 class="titulo">{{produto.nome}}</h2>
            <p class="preco">{{produto.preco}}</p>

        </div>
  </section>
</template>

<script>
export default {
    data(){
        return{
            produtos: null,
        }
    },

    methods: {
        getProdutos(){
            fetch("http://localhost:3004/produto").then(response => response.json()).then(response => {
                this.produtos = response;
            })
        }
    },

    created() {
        this.getProdutos();
    
    }
}
</script>

<style scoped>


</style>