<template>
    <div class="card" style="width: 30rem;">
        <img class="card-img-top" :src="this.url" alt="">
        <div class="card-body">
            <h3 class="card-title">{{this.titulo}}</h3>
            <p class="card-text">Valor en USD: ${{cotizacion.usd}}</p>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        iconoURL: String,
        titulo: String,
        cotizacion: Number
    },
    computed: {
        url: function() {
        return `../img/icons/${this.iconoURL}`;
        }
    },
    data: () => ({
    //
  }),
};
</script>

<style scoped>
p {
    margin: 20px 0px;
}
</style>