<template>
    <div class="container">
        <div class="row">
            <h2>Cotizaciones del dólar en Argentina</h2>
        </div>
        <div class="row justify-content-center">
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionDolarCard :iconoURL="this.iconoURL" :cotizacion="this.cotizacionesDolar[0].casa"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionDolarCard :iconoURL="this.iconoURL" :cotizacion="this.cotizacionesDolar[1].casa"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionDolarCard :iconoURL="this.iconoURL" :cotizacion="this.cotizacionesDolar[3].casa"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionDolarCard :iconoURL="this.iconoURL" :cotizacion="this.cotizacionesDolar[4].casa"/>
            </div>
        </div>
    </div>
</template>

<script>

import CotizacionDolarCard from "./CotizacionDolarCard.vue";

export default {
    components: {
        CotizacionDolarCard
    },
    created: async function () {
        let fetchCotizaciones = await fetch("https://www.dolarsi.com/api/api.php?type=valoresprincipales")
        this.cotizacionesDolar = await fetchCotizaciones.json()
    },
    data: () => ({
        cotizacionesDolar: {},
        iconoURL: "dollar.svg"
    }),
};
</script>
<style scoped>
h2 {
    margin:auto;
    margin-bottom: 30px;
    vertical-align:middle;
}
</style>