# v-scroll-progression

Scroll progress indicator component for Vue 2.

## Installation

```bash
# Using NPM
npm install v-scroll-progression
# Using Yarn
yarn add v-scroll-progression
```

Register the component:

```js
import VScrollProgression from "v-scroll-progression";

Vue.use(VScrollProgression);
```

### Nuxt 2

Create a file called `v-scroll-progression.client.js` in your `plugins/` folder. In there put the following:

```js
import Vue from "vue";
import VScrollProgression from "v-scroll-progression";

Vue.use(VScrollProgression);
```

Next, open your `nuxt.config.js` and add `~/plugins/v-scroll-progression.js` to the `plugins` array.

## Usage

U can use the component in any of your components by using the `<v-scroll-progression/>` or `<VScrollProgression/>` tag.

## Props

| Name         | Type               | Required | Default Value | Allowed Values  | Description                            |
| :----------- | :----------------- | :------- | :------------ | :-------------- | :------------------------------------- |
| `color`      | `String`           | `false`  | `#41B883`     |                 | Color of the progress indicator.       |
| `background` | `String`           | `false`  | `#35495E`     |                 | Background color of the progress bar.  |
| `height`     | `String`, `Number` | `false`  | `5px`         |                 | Height of the progress bar.            |
| `placement`  | `String`           | `false`  | `top`         | `bottom`, `top` | Sets the placement of the progess bar. |

## License
The MIT License (MIT). Please see the [License File](LICENSE.md) for more information.