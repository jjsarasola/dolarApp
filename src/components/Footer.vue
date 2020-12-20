<template>
  <v-footer
    app
    dark
    padless
  >
    <v-card
      class="flex"
      flat
      tile
    >
      <v-card-title class="teal">
        <strong class="subheading">Redes sociales</strong>

        <v-btn
          class="mx-4"
          dark
          icon
          @click="linkedin()"
        >
          <v-icon size="24px">
            {{ this.icons[0] }}
          </v-icon>
        </v-btn>

        <v-btn
          class="mx-4"
          dark
          icon
          @click="github()"
        >
          <v-icon size="24px">
            {{ this.icons[1] }}
          </v-icon>
        </v-btn>

      </v-card-title>

      <v-card-text class="py-2 white--text text-center">
        {{ new Date().getFullYear() }} — <strong>Juan José Sarasola</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>
<script>
  export default {
    data: () => ({
      icons: [
        'mdi-linkedin',
        'mdi-github',
      ],
    }),
    methods: {
      linkedin: function () {
        var win = window.open("https://www.linkedin.com/in/juan-jos%C3%A9-sarasola/", '_blank');
        win.focus()
      },
      github: function () {
        var win = window.open("https://github.com/jjsarasola/", '_blank');
        win.focus()
      }
    }
  }
</script>