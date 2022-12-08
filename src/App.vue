/* App.vue */
<script>
import ListaDeProdutos from './components/ListaDeProdutos.vue'
import ProdutosSelecionados from './components/ProdutosSelecionados.vue'

export default {
  components: { ListaDeProdutos, ProdutosSelecionados },
  data() {
    return {
      produtosSelecionados: [],
    }
  },
  methods: {
    selecionarProduto: function(produto) {
      this.produtosSelecionados.push(produto);
    }
  }
}
</script>

<template>
  <ProdutosSelecionados
    :produtosSelecionados="produtosSelecionados"
  />

  <ListaDeProdutos
    @produto-selecionado="selecionarProduto"
  />
</template>

<style scoped>
</style>
