<template>
  <hooper
    style="height: 100%"
    :progress="true"
    :autoPlay="true"
    :playSpeed="2000"
  >
    <slide>
      <img
        class="h-screen w-full object-cover object-bottom"
        src="../assets/images/page1.jpg"
      />
      <p class="z-50">Luangkan harimu</p>
    </slide>
    <slide>
      <img
        class="h-screen w-full object-cover object-center"
        src="../assets/images/page2.jpg"
      />
    </slide>
    <hooper-pagination slot="hooper-addons"></hooper-pagination>
  </hooper>
</template>

<script>
import { Hooper, Slide, Pagination as HooperPagination } from "hooper";
import "hooper/dist/hooper.css";

export default {
  name: "App",
  components: {
    Hooper,
    Slide,
    HooperPagination,
  },
};
</script>
