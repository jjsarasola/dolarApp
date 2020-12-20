<template>
    <div class="card" style="width: 30rem;">
        <img class="card-img-top" :src="this.url" alt="">
        <div class="card-body">
            <h3 class="card-title">{{cotizacion.nombre}}</h3>
            <p class="card-text">Compra: ${{cotizacion.compra}}</p>
            <p class="card-text">Venta: ${{cotizacion.venta}}</p>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        iconoURL: String,
        cotizacion: Object
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