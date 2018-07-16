<template>
  <div class="mainContainer">
    <el-container>
      <el-aside width="200px">TOC</el-aside>
      <el-container>
        <el-header>Toolbar</el-header>
        <el-main>
          <div id="map"></div>
        </el-main>
      </el-container>
    </el-container>

  </div>
</template>

<script>
import mapboxgl from "mapbox-gl";
export default {
  name: "mainMap",
  props: {},
  data() {
    return {
      map: null
    };
  },
  mounted() {
    this.initMap();
  },
  methods: {
    initMap() {
      var style = {
        version: 8,
        name: "Bright",
        sources: {},
        center: [108.35634196000183, 33.4908120773096],
        zoom: 4,
        // "sprite": "http://localhost:8080/new-mbg/sprites/sprite",
        // "glyphs": "http://localhost:8080/new-mbg/glyphs/{fontstack}/{range}.pbf",
        layers: [
          {
            type: "background",
            layout: {
              visibility: "visible"
            },
            paint: {
              "background-color": "#87c2e4"
            },
            id: "0"
          }
        ]
      };
      if (!mapboxgl.supported()) {
        // console.error("您的浏览器不支持WebGL,请升级到最新版本。");
        return;
      }
      this.map = new mapboxgl.Map({
        container: "map",
        style: style
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.mainContainer,
.el-container,
.el-main,
#map {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
}
/* #map {
  background-color: aqua;
} */
.el-header {
  background-color: #b3c0d1;
  /* color: #333; */
  /* text-align: center; */
  /* line-height: 60px; */
}

.el-aside {
  background-color: #d3dce6;
  /* color: #333; */
  /* text-align: center; */
}

.el-main {
  background-color: #f07ea0;
  /* color: #333; */
  /* text-align: center; */
  /* line-height: 160px; */
}
</style>
