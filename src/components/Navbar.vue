<template>
    <v-app-bar
    app
      absolute
      color="#fcb69f"
      dark
      shrink-on-scroll
      src="..\img\NavDolar.jpg"
      scroll-target="#scrolling-techniques-2"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        ></v-img>
      </template>

      <v-toolbar-title>DolarApp</v-toolbar-title>
    </v-app-bar>
    
</template>