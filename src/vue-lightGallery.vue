<template>
  <div :id="id" class="list-unstyled justified-gallery"></div>
</template>
<script>
import "lightgallery.js";
import "lightgallery.js/dist/css/lightgallery.min.css";

export default {
  name: "lightGallery",
  props: {
    images: {
      type: Array,
      required: true
    },
    id: {
      type: String,
      default: "lightgallery"
    }
  },
  data () {
    return {};
  },
  methods: {
    showImage (index) {
      var lg = document.getElementById(this.id);
      lg.addEventListener(
        "onAfterOpen",
        function (event) {
          let obj = document.querySelector("iframe.lg-object");
          obj && obj.setAttribute("scrolling", "no");
        },
        { once: true }
      );
      if (lg.getAttribute("lg-uid")) {
        window.lgData[lg.getAttribute("lg-uid")].s.index = index;
      }
      window.lightGallery(lg, {
        dynamic: true,
        dynamicEl: this.images,
        index: index,
        preload: 0,
        iframeMaxWidth: "70%"
      });
    }
  }
}
</script>
