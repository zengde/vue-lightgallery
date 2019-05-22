<template>
  <div id="app">
    <ul>
      <li v-for="(v,k) in imgs" :key="v.img_id" @click="openGallery(k)">
        <img :src="v.src" title="点击播放视频" alt="点击播放视频" fluid top>
        <p>图片尺寸：{{v.info[0]}}*{{v.info[1]}}</p>
        <div slot="footer" class="text-muted">上传者：{{v.realname}}</div>
      </li>
    </ul>
    <lightGallery
      :images="modalGallerys"
      ref="lightGallery"
      :show-caption="true"
      :show-thumbs="true"
      :show-light-box="false"
    ></lightGallery>
  </div>
</template>

<script>
import lightGallery from "./vue-lightGallery";
import "lg-zoom.js";
import "lg-fullscreen.js";
import "lg-thumbnail.js";
import "lg-autoplay.js";

export default {
  name: "app",
  data () {
    return {
      msg: "Welcome to Your Vue.js App",
      imgs: [
        {
          src: "https://sachinchoolur.github.io/lightgallery.js/static/img/1.jpg",
          thumb: "https://sachinchoolur.github.io/lightgallery.js/static/img/thumb-1.jpg",
          info: [600, 800],
          realname: "admin"
        },
        {
          src: "https://sachinchoolur.github.io/lightgallery.js/static/img/2.jpg",
          thumb: "https://sachinchoolur.github.io/lightgallery.js/static/img/thumb-2.jpg",
          info: [600, 800],
          realname: "admin"
        },
        {
          src: "https://sachinchoolur.github.io/lightgallery.js/static/img/13.jpg",
          thumb: "https://sachinchoolur.github.io/lightgallery.js/static/img/thumb-13.jpg",
          info: [600, 800],
          realname: "admin"
        }
      ]
    };
  },
  components: {
    lightGallery
  },
  computed: {
    modalGallerys () {
      var arr = [];
      this.imgs.forEach((value, index) => {
        let obj = {
          subHtml: "图片尺寸：" +
            value.info[0] +
            "*" +
            value.info[1] +
            "<br>上传者:" +
            value.realname,
          thumb: value.thumb,
          src: value.src
        };
        arr.push(obj);
      });
      return arr;
    }
  },
  methods: {
    openGallery (index) {
      this.$refs.lightGallery.showImage(index);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
  display: flex;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
img {
  max-width: 100%;
}
</style>
