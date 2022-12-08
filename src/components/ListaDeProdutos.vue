<script>
export default {
    data() {
        return {
            produtos: [
                { nome: 'Moletom', preco: 200 },
                { nome: 'Jaqueta', preco: 250 },
            ],
        }
    },
    methods: {
        selecionarProduto: function(produto) {
            this.$emit('produto-selecionado', produto);
        }
    }
}
</script>

<template>
    <div>
        Lista de produtos
        <ul>
            <li v-for="p in produtos"
                @click="selecionarProduto(p)"
            >
                {{ p.nome }}: {{ p.preco }}
            </li>
        </ul>
    </div>
</template>

<style scoped />
