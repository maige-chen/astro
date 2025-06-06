---
layout: ../../layout/Markdown.astro
title: "astro安装使用教程"
pubDate: 2025-06-05
description: "这是我 Astro 博客的第一篇文章。"
author: "Astro Maige"
image:
  url: "https://docs.astro.build/assets/rose.webp"
  alt: "The Astro logo on a dark background with a pink glow."
tags: ["astro", "blogging", "learning in public"]
---

# astro 宇宙

- 以内容驱动的网站前端框架, 减少 javascript 开销
- 开创"群岛"理念, 页面上 独立交互式 UI 组件
- 默认使用 vite 作为服务器

## 1. 安装

```text
    npm create astro@latest <项目文件夹名称>
    npm run dev             # http://localhost:4321
    npm run build

    npx @astrojs/upgrade    # 升级
    npm install astro       # 手动升级
    pnpm install astro
    yarn add astro
```

## 2. css 变量的使用

```text
    1. 定义变量
    ---
    const skillColor = "navy";
    ---

    2. <style define:vars={{skillColor}}>...</style>
    使用 define:vars 定义style中可用的变了！

    3. 使用
    .skill {
		color: var(--skillColor);
    }
```

## 3. astro + vue

### 3.1 基本安装备注

```text
    pnpm astro add vue
    本质：
    1.安装依赖 pnpm add @astrojs/vue vue
    2.配置astro.config.mjs
        import { defineConfig } from 'astro/config';
        import vue from "@astrojs/vue";
        export default defineConfig({
            integrations: [vue()],
        });
```

### 3.2 基本使用

```text
    vi ./src/components/vue/Button.vue

    <script setup>
        import { ref, reactive, onMounted } from "vue";
        const count = ref(0);
    </script>
    <template>
        <button @click="count++">You clicked me {{ count }} times.</button>
    </template>
```

```text
    vi ./src/pages/vue.astro

    ---
    import Layout from '../layouts/Layout.astro';
    import VueButton from '../components/vue/VueButton.vue';
    ---
    <Layout title='Welcome to "Astro+vue".'>
        <VueButton client:visible />            # client:xx 需要激活
    </Layout>
```

### 3.3 appEntrypoint: astro + ElementPlus

```text

```
