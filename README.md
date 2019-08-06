##  fade-comp 

**fade-comp** is a Vue.js (version >= 2.5) component that fades in/out content .  Any html content that is surrounded by the **fade-com** tags will be subject to fading either vertically or horizontally.

 **fade-comp** depends on the [vue.js](https://vuejs.org/ "Vue.js") framework and can be installed via [npm install](https://docs.npmjs.com/cli/install.html "npm install") with the included `package.json` file.  Three [webpack](https://webpack.js.org/concepts/) npm scripts are included for building  development, production, or hot recompile/execute of the demo.   `build-dev` and `build-prod` scripts produce  a `dist` folder containing the `index.html`.  The size of the `main.js` bundle using `build-prod` is 9 KiB along with calling a CDN for incorporating the Vue framework.

## Props

A prop in Vue.js is a custom attribute for passing information from a parent component hosting **fade-comp** instance(s) to a **fade-comp** as a child component. 

**fade-comp** has the following prop:

`direction` -- the direction of the fade (string; either `vertical` or `horizontal`)

`out` -- a boolean which tells  **fade-com** to fade out the content if true; fades in if false

## Styling

**fade-comp** does not have any styling variables.

## Events

**fade-comp** does not have any events.

## Demonstration

A demonstration of **fade-comp** is provided in the folder named `dist` and can be viewed by hosting the `index.html`file.  The demo (templated in the `App.vue` file) has a single  **fade-com** child which fades in/out and vertically/horizontally some string content.

As a suggestion, install [http-server](https://www.npmjs.com/package/http-server "http-server") globally via [npm](https://www.npmjs.com/ "npm") then enter the command `http-server`in the **fade-com** `dist` directory.  From a browser enter the url: `localhost:8080/` to view the demo.

Here is some example code for using **fade-com** taken from the demo:

```
      <section id="button _box">
        <button v-on:click="fade_out_height">Fade Out Height</button>
        <button v-on:click="fade_in_height">Fade In Height</button>
        <button v-on:click="fade_out_left">Fade Out Left</button>
        <button v-on:click="fade_in_left">Fade In Left</button>
      </section>
      <fade-comp
        :direction="direction"
        :out="out">
        <div id="mess">
          Happy Birthday
        </div>
      </fade-comp>
```

And the supporting data references:

```
  data() {
    return {
      direction: null,
      out: null
    }
  },
  methods: {
    //parent to child methods -- setting properties
    fade_out_height: function(){
      this.direction = 'vertical';
      this.out = true;
    },
    fade_in_height: function(){
      this.direction = 'vertical';
      this.out = false;
    },
    fade_out_left: function(){
      this.direction = 'horizontal';
      this.out = true;
    },
    fade_in_left: function(){
      this.direction = 'horizontal';
      this.out = false;
    }
  }
```

