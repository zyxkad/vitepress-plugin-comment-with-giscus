# README

EN | [中文文档](README_zh.md)

## vitepress-plugin-comment-with-giscus

![](demo.png)

> `vitepress` comment section plugin based on `giscus`

## Install

```shell
// npm
npm i vitepress-plugin-comment-with-giscus
// yarn
yarn add vitepress-plugin-comment-with-giscus
```

## Usage

```ts
// .vitepress/theme/index.js
import DefaultTheme from 'vitepress/theme';
import giscusTalk from 'vitepress-plugin-comment-with-giscus';
import { useData } from 'vitepress';
export default {
    ...DefaultTheme,
    enhanceApp(ctx) {
        DefaultTheme.enhanceApp(ctx);
        // ...
    },
    setup() {
        // Get frontmatter
        const { frontmatter } = useData();
        // Comment component
        giscusTalk(frontmatter, {
            repo: 'your github repository',
            repoId: 'your repository id',
            categoryId: 'your category id',
            mapping: 'pathname'
        });
    }
};
```

For the parameter acquisition method of `giscus`, please refer to：[giscus configuration](https://giscus.app/)

## Extended

If the following code is added to the preface of the article, the comment area will not be generated

```md
---
comment: false
---
```
