<template>
  <div class="home">
    <HomeComponent msg="Color Converter v0.1"/>
    <chrome-picker v-model="colors" />
    <br>
    <p>
      <strong>RGBA</strong>
      {{colors.rgba}}
    </p>
    <p>
      <strong>Int representation</strong>
      {{getIntFromARGB((colors.rgba.a * 255), colors.rgba.r, colors.rgba.g, colors.rgba.b)}}
    </p>
  </div>
</template>

<script>
// @ is an alias to /src
import { Chrome } from 'vue-color';
import HomeComponent from '@/components/HomeComponent.vue';

export default {
  name: 'Home',
  components: {
    HomeComponent,
    'chrome-picker': Chrome,
  },
  data() {
    return {
      colors: {
        hex: '#194d33',
        hex8: '#194D33A8',
        hsl: {
          h: 150, s: 0.5, l: 0.2, a: 1,
        },
        hsv: {
          h: 150, s: 0.66, v: 0.30, a: 1,
        },
        rgba: {
          r: 25, g: 77, b: 51, a: 1,
        },
        a: 1,
      },
    };
  },
  methods: {
    getIntFromARGB(alpha, red, green, blue) {
      // eslint-disable-next-line no-bitwise
      return (alpha << 24) | (red << 16) | (green << 8) | blue;
    },
  },
};
</script>

<style lang="scss">
  .home {
    .vc-chrome {
      width: 100%;
      max-width: 400px;
      margin: auto;
    }
  }
</style>
