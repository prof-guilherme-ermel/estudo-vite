/* App.vue */
<script>
import ListaDeProdutos from './components/ListaDeProdutos.vue'
import ProdutosSelecionados from './components/ProdutosSelecionados.vue'

export default {
  components: { ListaDeProdutos, ProdutosSelecionados },
  data() {
    return {
      selecionados: [],
    }
  },
  methods: {
    selecionarProduto: function(produto) {
      this.selecionados.push(produto);
    }
  }
}
</script>

<template>
  <ProdutosSelecionados
    :itens-selecionados="selecionados"
  />

  <ListaDeProdutos
    @produto-selecionado="selecionarProduto"
  />
</template>

<style scoped>
</style>
