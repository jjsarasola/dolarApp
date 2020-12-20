<template>
  <v-app>
    <Navbar />
    <v-main>
      <v-container>
        <CotizacionDolar />
        <CotizacionCrypto />
      </v-container>
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import CotizacionDolar from "./components/CotizacionDolar.vue";
import CotizacionCrypto from "./components/CotizacionCrypto.vue";
import Footer from "./components/Footer.vue";
export default {
  name: 'DolarApp',

  components: {
    Navbar,
    CotizacionDolar,
    CotizacionCrypto,
    Footer
  },

  data: () => ({
    //
  }),
};
</script>
