<script>
export default {
    props: {
        produtosSelecionados: {
            type: Array,
            required: true,
        }
    }
}
</script>

<template>
    <div>
        Produtos selecionados
        <ul>
        <li v-for="p in produtosSelecionados">
            {{ p.nome }}: {{ p.preco }}
        </li>
        </ul>
  </div>
</template>

<style scoped />
