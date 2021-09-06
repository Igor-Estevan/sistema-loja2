<template>
  <div class="clientes">
    <Header />
    <div class="container container-clientes">
      <div class="row">
        <div class="col-md-12">
          <h2>Página em Desenvolvimento...</h2>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>
<script>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";

export default {
  name: "clientes",
  components: {
    Header,
    Footer,
  },
};
</script>
<style>
.container-clientes {
  text-align: center;
  padding: 100px;
}
</style>