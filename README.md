### Introduction

vue wrapper of [lightgallery.js](https://github.com/sachinchoolur/lightgallery.js)

[online demo](https://zengde.github.io/vue/#/lightGallery) 

### Start

1. Install

    ```
    $ npm install lightgallery-vue@latest
    ```

2. Usage

    Step 1. Add lightgallery-vue component
    ```js
    import lightGallery from 'lightGallery-vue';
    export default {
      components:{
        lightGallery
      }
    }
    ```

    Step 2. Use in template
    ```html
    <lightGallery 
		:images="modalGallerys" 
		ref="lightGallery">
	</lightGallery>
    ```
	with multi add id prop
    ```html
    <lightGallery 
		id="lightGallery2"
		:images="modalGallerys" 
		ref="lightGallery">
	</lightGallery>
    ```


    Step 3. Config for lightGallery
    ```js
    export default {
      data () {
        return {
          images: [{
            src: '1.jpg',
			thumb:'2.jpg',
			subHtml:'caption'
          }{
            src: '1.html',
			thumb:'2.jpg',
			subHtml:'',
			iframe:true
          }]
        }
      }
    }
    ```

#### Attributes

[Dynamic variables](https://sachinchoolur.github.io/lightgallery.js/docs/api.html#dynamic)


#### Method

```js
this.$refs.lightGallery.showImage(index);
```
[More methods](https://sachinchoolur.github.io/lightgallery.js/docs/api.html#methods)

#### Event

[More events](https://sachinchoolur.github.io/lightgallery.js/docs/api.html#methods)

### Plugins

lightgallery supports your custom plugins for more content viewing [plugins](https://github.com/sachinchoolur/lightgallery.js#built-in-modules)

```js
import lightGallery from 'lightGallery-vue';
import 'lg-zoom.js';
import 'lg-fullscreen.js';
import 'lg-thumbnail.js';
import 'lg-autoplay.js';
```

### Demo

```
$ git clone git@github.com:zengde/vue-lightgallery.git
$ cd vue-lightgallery
$ npm install
$ npm run dev
```

please visit [http://localhost:8080/](http://localhost:8080/)


### License

[MIT](http://opensource.org/licenses/MIT)