<script>
export default {
    props: {
        itensSelecionados: {
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
        <li v-for="item in itensSelecionados">
            {{ item.nome }}: {{ item.valor }}
        </li>
        </ul>
  </div>
</template>

<style scoped />
