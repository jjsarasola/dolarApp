<template>
    <div class="container">
        <div class="row">
            <h2>Cotizaciones del mercado crypto</h2>
        </div>
        <div class="row justify-content-center">
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionCryptoCard :iconoURL="this.iconoBTC" :titulo="this.titulos.btc" :cotizacion="this.cotizacionesCrypto.bitcoin"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionCryptoCard :iconoURL="this.iconoETH" :titulo="this.titulos.eth" :cotizacion="this.cotizacionesCrypto.ethereum"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionCryptoCard :iconoURL="this.iconoXRP" :titulo="this.titulos.xrp" :cotizacion="this.cotizacionesCrypto.ripple"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionCryptoCard :iconoURL="this.iconoBNB" :titulo="this.titulos.bnb" :cotizacion="this.cotizacionesCrypto.binancecoin"/>
            </div>
        </div>
        <div class="row justify-content-center">
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionCryptoCard :iconoURL="this.iconoLTC" :titulo="this.titulos.ltc" :cotizacion="this.cotizacionesCrypto.litecoin"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionCryptoCard :iconoURL="this.iconoXLM" :titulo="this.titulos.xlm" :cotizacion="this.cotizacionesCrypto.stellar"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionCryptoCard :iconoURL="this.iconoADA" :titulo="this.titulos.ada" :cotizacion="this.cotizacionesCrypto.cardano"/>
            </div>
            <div class="col-sm-6 col-md-3 text-center">
                <CotizacionCryptoCard :iconoURL="this.iconoBCH" :titulo="this.titulos.bch" :cotizacion="this.cotizacionesCrypto['bitcoin-cash']"/>
            </div>
        </div>
    </div>
</template>

<script>

import CotizacionCryptoCard from "./CotizacionCryptoCard.vue";

export default {
    components: {
        CotizacionCryptoCard
    },
    created: async function () {
        let fetchCotizaciones = await fetch("https://api.coingecko.com/api/v3/simple/price?ids=bitcoin%2Cethereum%2Cripple%2Clitecoin%2Cbitcoin-cash%2Cbinancecoin%2Ccardano%2Cstellar&vs_currencies=usd")
        this.cotizacionesCrypto = await fetchCotizaciones.json()
    },
    data: () => ({
        cotizacionesCrypto: {},
        titulos: {
            btc: "Bitcoin (BTC)",
            eth: "Ethereum (ETH)",
            xrp: "Ripple (XRP)",
            bnb: "Binance (BNB)",
            ltc: "Litecoin (LTC)",
            xlm: "Stellar (XLM)",
            ada: "Cardano (ADA)",
            bch: "Bitcoin Cash (BCH)",
        },
        iconoBTC: "btc.png",
        iconoETH: "eth.png",
        iconoXRP: "xrp.png",
        iconoBNB: "bnb.png",
        iconoLTC: "ltc.png",
        iconoXLM: "xlm.png",
        iconoADA: "ada.png",
        iconoBCH: "bch.png",
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