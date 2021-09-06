<template>
  <section class="pedidos">
    <Header />
    <div class="container container_pedidos">
      <div class="row">
        <div class="col-md-12">
          <h2>Todos os pedidos</h2>
        </div>
      </div>
      <div class="row">
        <div v-for="pedido in pedidos" :key="pedido._id" class="col-md-12">
          <div class="pedidos_card">
            <p>Código Produto: {{ pedido.produtoId }}</p>
            <p>CPF: {{ pedido.clienteCPF }}</p>
            <p>Valor Unitário: R$ {{ pedido.valorUnitario }}</p>
            <p>Valor Total: R$ {{ pedido.ValorTotal }}</p>
            <p>Quantidade: {{ pedido.quantidade }}</p>
          </div>
        </div>
      </div>
    </div>
    <Footer />
  </section>
</template>

<script>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
export default {
  name: "Pedidos",
  components: {
    Header,
    Footer,
  },
  data: function () {
    return {
      pedidos: [],
    };
  },
  methods: {
    getPedidos: async function () {
      const result = await fetch("http://localhost:3000/pedidos")
        .then((res) => res.json())
        .catch((error) => {
          return {
            error: true,
            message: error,
          };
        });
      if (!result.error) {
        this.pedidos = result;
      }
    },
  },
  created: function () {
    this.getPedidos();
  },
};
</script>

<style>
.pedidos_card {
  border: 1px solid black;
  padding-left: 20px;
  margin: 10px 0;
}

</style>