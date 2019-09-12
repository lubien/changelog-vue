<template>
  <div id="app">
    <Changelog :changelog="changelog"/>
  </div>
</template>

<script>
import Changelog from "@/components/Changelog";

export default {
  name: "App",
  components: {
    Changelog
  },

  data: () => ({
    changelog: [
      {
        version: "3.23.2",
        date: "2019-09-06",
        entries: [
          {
            title: "Conserta o botão",
            reference: "18701",
            author: "yoyo837",
            entries: [
              {
                title: "Conserta botões pequenos",
                reference: "18702",
                author: "yoyo837"
              },
              {
                title: "Conserta botões grandes",
                reference: "18703",
                author: "yoyo837"
              }
            ]
          }
        ]
      },

      {
        version: "3.23.1",
        date: "2019-09-05",
        entries: [
          {
            title: "Conserta a barra lateral",
            reference: "18600",
            author: "peao837",
            entries: [
              {
                title: "Conserta scroll",
                reference: "18602",
                author: "peao837"
              },
              {
                title: "Conserta posição",
                reference: "18603",
                author: "peao837"
              }
            ]
          }
        ]
      }
    ]
  })
};
</script>

<style>
body {
  background-color: #fefefe;
}

#app {
  /* text-align: center; */
  padding: 20px;
}
</style>
