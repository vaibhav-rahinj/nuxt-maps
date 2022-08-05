<template>
  <main class="w-screen h-screen">
    <v-map class="w-full h-full" :options="state.map" />
  </main>
</template>
<script lang="ts">
import VMap from "v-mapbox";
export default defineComponent({
  name: "CommonMap",
  components: {
    VMap,
  },
  setup() {
    const state = reactive({
      map: {
        container: "map",
        accessToken:
          "pk.eyJ1IjoidmFpYmhhdnJhaGluaiIsImEiOiJjbDZnYjJpNzQwY3NhM2NvNjJuNW9hb2QwIn0.UjvPccYOtfE9kZ6w3CTkIw",
        style: "mapbox://styles/mapbox/streets-v11?optimize=true",
        // style: "https://basemaps.cartocdn.com/gl/dark-matter-gl-style/style.json",
        center: [73.7868, 18.559] as number[],
        zoom: 2,
        maxZoom: 22,
        crossSourceCollisions: false,
        failIfMajorPerformanceCaveat: false,
        preserveDrawingBuffer: true,
        hash: false,
        minPitch: 0,
        attributionControl: false,
        maxPitch: 60,
      },
    });
    return {
      state,
    };
  },
});
</script>
<style>
.w-screen {
  width: 100vw;
}
.h-screen {
  height: 100vh;
}
.h-full {
  height: 100%;
}
.w-full {
  width: 100%;
}
</style>
