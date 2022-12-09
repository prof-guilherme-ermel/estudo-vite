<script>
export default {
    data() {
        return {
            produtos: [],
        }
    },
    created: function() {
        this.carregarProdutos();
    },
    methods: {
        carregarProdutos: async function() {
            const resposta = await fetch('http://localhost:3000/produtos');
            const dados = await resposta.json();
            if (dados.error) {
                return alert(dados.error);
            }
            this.produtos = dados.produtos;
        },
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
