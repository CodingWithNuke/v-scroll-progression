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

## Usage

U can use the component in any of your components by using the `<v-scroll-progression/>` or `<VScrollProgression/>` tag.

## Props

| Name         | Type               | Required | Default Value | Description                                         |
| ------------ | ------------------ | -------- | ------------- | --------------------------------------------------- |
| `color`      | `String`           | `false`  | `#41B883`     | Color of the progress indicator.                    |
| `background` | `String`           | `false`  | `#35495E`     | Background color of the progress bar.               |
| `height`     | `String`, `Number` | `false`  | `5px`         | Height of the progress bar.                         |
| `absolute`   | `Boolean`          | `false`  | `false`       | Sets the position to `absolute` instead of `fixed`. |
| `bottom`     | `Boolean`          | `false`  | `false`       | Sets the `bottom` style to `0`.                     |