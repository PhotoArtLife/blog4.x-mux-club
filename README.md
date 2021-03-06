Blog 4.x built with Vue 2.x + vue-router + vuex, with server-side rendering.

- 一个基于 Vue2.x、Vuex、Webpack4.x、UI 库、Request 库等配置完善的 SSR 脚手架

## Features

> Note: in practice, it is unnecessary to code-split for an app of this size (where each async chunk is only a few kilobytes), nor is it optimal to extract an extra CSS file (which is only 1kb) -- they are used simply because this is a demo app showcasing all the supported features.

- Server Side Rendering
  - Vue + vue-router + vuex working together
  - Server-side data pre-fetching
  - Client-side state & DOM hydration
  - Automatically inlines CSS used by rendered components only
  - Preload / prefetch resource hints
  - Route-level code splitting
- Progressive Web App
  - App manifest
  - Service worker
  - 100/100 Lighthouse score
- Single-file Vue Components
  - Hot-reload in development
  - CSS extraction for production
- Animation
  - Effects when switching route views
  - Real-time list updates with FLIP Animation

## Upgrade Log

- 构建工具 Webpack 由 3.x 升级到 4.x，更新了处理 js、css 的 loader 和 plugins
- 引入 style-resources-loader，全局引入 mixin 和 function、animate less，组件和业务层不用重复 import，聚合 less 的使用能力和场景

## A Note on Performance

This is a demo primarily aimed at explaining how to build a server-side rendered Vue app, as a companion to our SSR documentation. There are a few things we probably won't do in production if we were optimizing for performance, for example:

- This demo uses the Firebase-based HN API to showcase real-time updates, but the Firebase API also comes with a larger bundle, more JavaScript to parse on the client, and doesn't offer an efficient way to batch-fetch pages of items, so it impacts performance quite a bit on a cold start or cache miss.

- In practice, it is unnecessary to code-split for an app of this size (where each async chunk is only a few kilobytes so the extra request isn't really worth it), nor is it optimal to extract an extra CSS file (which is only 1kb).

It is therefore not recommended to use this app as a reference for Vue SSR performance - instead, do your own benchmarking, and make sure to measure and optimize based on your actual app constraints.

**A detailed Vue SSR guide can be found [here](https://ssr.vuejs.org).**

## Build Setup

**Requires Node.js 7+**

```bash
# install dependencies
npm install # or yarn

# serve in dev mode, with hot reload at localhost:8080
npm run dev

# build for production
npm run build

# serve in production mode
npm start
```

## License

MIT
