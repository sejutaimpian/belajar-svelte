<details id="top">
  <summary>DAFTAR ISI</summary>
  <ol>
    <li>
        <a href="#1-introduction">Introduction</a>
    </li>
    <li>
        <a href="#2-setting-up-a-svelte-app">Setting up a Svelte App</a>
    </li>
  </ol>
</details>

# Tentang Repo

Repo ini saya buat sebagai riwayat sekaligus rangkuman belajar materi svelte. Acuan belajar dari [The Net Ninja](https://youtube.com/playlist?list=PL4cUxeGkcC9hlbrVO_2QFVqVPhlZmz7tO) tapi dicompare dengan materi terbaru pada [dokumentasi resmi svelte](https://svelte.dev/docs). Versi yang saya gunakan adalah Svelte versi 3.54.0

# 1. Introduction

- Svelte is compiler for creating reactive web apps & interfaces
- Can be used for small parts of a site, or entirely (SPA)
- Install extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode)

# 2. Setting up a Svelte App

- Harus intall nodejs
- Install tidak lagi menggunakan degit, tapi melalui [vite](https://vitejs.dev/guide/#scaffolding-your-first-vite-project)

```sh
npm create vite@latest my-svelte-app -- --template svelte
cd my-svelte-app
npm i
npm run dev
```

- Struktur folder sudah banyak perubahan, tidak seperti pada acuan.
