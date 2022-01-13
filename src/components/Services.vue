<template>
  <div class="container">
    <h1 class="heading">services</h1>
    <div class="box-container" id="lightgallery">
      <a
        class="box"
        v-for="(item, i) in services"
        :key="i"
        :href="item.src"
        :data-sub-html="`<h1>${item.h3}</h1><p>${item.p}</p>`"
      >
        <img :src="item.src" alt="" />

        <h3>{{ item.h3 }}</h3>
        <p>
          {{ item.p }}
        </p>
      </a>
      <!-- <a href="#" class="btn">{{ item.btnText }}</a> -->
    </div>
  </div>
</template>

<script>
import { services } from "../utils/serviceList";
import "lightgallery.js";
import "lightgallery.js/dist/css/lightgallery.css";
export default {
  data() {
    return {
      services: services,
    };
  },
  mounted() {
    const el = document.getElementById("lightgallery");
    window.lightGallery(el);
  },
};
</script>
