<template>
  <div
    :class="{
      'v-scroll-progression': true,
      'v-scroll-progression--top': placement == 'top',
      'v-scroll-progression--bottom': placement == 'bottom',
    }"
    :style="{
      height: convertToUnit(height),
      background: background,
    }"
  >
    <div
      class="v-scroll-progression__progress"
      :style="{ background: color, width: progress }"
    />
  </div>
</template>

<script lang="ts">
import { PropType } from "vue";

import { convertToUnit } from "./utils/helpers";

export default {
  name: "v-scroll-progression",

  props: {
    color: {
      type: String as PropType<string>,
      default: "#41B883",
    },
    background: {
      type: String as PropType<string>,
      default: "#35495E",
    },
    height: {
      type: [String, Number] as PropType<string | number>,
      default: "5px",
    },
    placement: {
      type: String as PropType<string>,
      default: "top",
      validator: (v) => ["bottom", "top"].includes(v),
    },
  },

  data: () => ({
    scrollTop: null as null | number,
    documentHeight: null,
    progress: null,
  }),

  methods: {
    convertToUnit,
    scrollHandler() {
      this.scrollTop =
        document.body.scrollTop || document.documentElement.scrollTop;
      this.documentHeight =
        document.documentElement.scrollHeight -
        document.documentElement.clientHeight;
      this.progress = `${(this.scrollTop / this.documentHeight) * 100}%`;
    },
  },

  created() {
    window.addEventListener("load", this.scrollHandler);
    window.addEventListener("scroll", this.scrollHandler);
  },

  destroyed() {
    window.removeEventListener("load", this.scrollHandler);
    window.removeEventListener("scroll", this.scrollHandler);
  },
};
</script>

<style scoped>
.v-scroll-progression {
  left: 0;
  right: 0;
  z-index: 9999;
  width: 100%;
  position: fixed;
}
.v-scroll-progression.v-scroll-progression--bottom {
  bottom: 0;
}
.v-scroll-progression.v-scroll-progression--top {
  bottom: 0;
}

.v-scroll-progression__progress {
  height: 100%;
  width: 0px;
}
</style>
