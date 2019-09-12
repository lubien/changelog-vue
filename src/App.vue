<template>
  <div id="app">
    <ul class="changelog">
      <li v-for="(release, i) in changelog" :key="i" class="changelog-item">
        <div class="changelog-item-bar"></div>
        <div class="changelog-item-star"></div>
        <div class="changelog-item-content">
          <h2 class="changelog-item-version">{{ release.version }}</h2>
          <code class="changelog-item-date">{{ release.date }}</code>
          <ul class="changelog-item-entries">
            <li v-for="(entry, j) in release.entries" :key="j" class="changelog-item-entry">
              {{ entry.title }}
              <a
                href="#"
                v-if="entry.reference"
                class="changelog-item-entry-ref"
              >#{{ entry.reference }}</a>
              <a href="#" v-if="entry.author">@{{ entry.author }}</a>

              <ul class="changelog-item-entries">
                <li v-for="(entry, k) in entry.entries" :key="k" class="changelog-item-entry">
                  <span>{{ entry.title }}</span>
                  <a
                    href="#"
                    v-if="entry.reference"
                    class="changelog-item-entry-ref"
                  >#{{ entry.reference }}</a>
                  <a href="#" v-if="entry.author">@{{ entry.author }}</a>
                </li>
              </ul>
            </li>
          </ul>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},

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
@import url("https://fonts.googleapis.com/css?family=Saira+Extra+Condensed|Source+Code+Pro&display=swap");

body {
  background-color: #fefefe;
}

#app {
  /* text-align: center; */
  padding: 20px;
}

.changelog {
  list-style: none;
  padding-left: 0;
  position: relative;
  line-height: 2;
  font-family: "Source Code Pro";
}

.changelog-item {
  padding-bottom: 20px;
  margin-bottom: -26px;
  position: relative;
}

.changelog-item a {
  text-decoration: none;
  color: #3498db;
}

.changelog-item-bar {
  position: absolute;
  border-left: 3px solid #dedede;
  height: 100%;
  margin-right: 20px;
}

.changelog-item-content {
  padding-left: 20px;
}

.changelog-item-version::before {
  /* content: "o"; */
  border: 3px solid #2980b9;
  background-color: white;
  /* width: 5px;
  height: 5px; */
  content: " ";
  font-size: 3.5px;
  border-radius: 50%;
  padding-right: 5px;
  /* color: 32980b9; */
  top: -9.5px;
  position: relative;
  margin: 36px;
  margin-right: 18px;
  margin-left: -24px;
  left: 0;
}

.changelog-item-version {
  font-size: 24px;
  color: #2c3e50;
  margin-bottom: 0;
  font-family: "Saira Extra Condensed";
  font-size: 24pt;
  letter-spacing: 3px;
}

.changelog-item-date {
  padding: 2px 8px;
  background-color: #ecf0f1;
  font-family: "Saira Extra Condensed";
  font-size: 16pt;
}

.changelog-item-entries {
  list-style: none;
  padding-left: 0;
}

.changelog-item-entries .changelog-item-entry {
  /* list-style-type: circle; */
  padding-left: 10px;
  line-height: 1.5;
}

.changelog-item-entry a {
  margin: 0 5px;
}

li.changelog-item-entry::before {
  position: relative;
  top: 2.5px;
  content: "\25e6";
  color: #858585;
  font-weight: bold;
  font-size: 22px;
  display: inline-block;
  width: 1em;
  /* padding-top: 2px; */
  /* margin-left: -1em; */
}

.changelog-item-entry .changelog-item-entries {
  padding-left: 23px;
}
</style>
