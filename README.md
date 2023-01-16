<details id="top">
  <summary>DAFTAR ISI</summary>
  <ol>
    <li>
        <a href="#1-introduction">Introduction</a>
    </li>
    <li>
        <a href="#2-setting-up-a-svelte-app">Setting up a Svelte App</a>
    </li>
    <li>
        <a href="#3-svelte-basics">Svelte Basics</a>
    </li>
    <li>
        <a href="#4-user-input--data-binding">User input & data binding</a>
    </li>
  </ol>
</details>

# Tentang Repo

Repo ini saya buat sebagai riwayat sekaligus rangkuman belajar materi svelte. Acuan belajar dari [The Net Ninja](https://youtube.com/playlist?list=PL4cUxeGkcC9hlbrVO_2QFVqVPhlZmz7tO) tapi dicompare dengan materi terbaru pada [dokumentasi resmi svelte](https://svelte.dev/docs). Versi yang saya gunakan adalah Svelte versi 3.54.0

# 1. Introduction

- Svelte is compiler for creating reactive web apps & interfaces
- Svelte is a tool for building fast web applications.
- Can be used for small parts of a site, or entirely (SPA)
- Install extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode)
- Svelte kini memiliki framework official bernama [SvelteKit](https://kit.svelte.dev/)

<p align="right"><a href="#top">Go 🔝</a></p>

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

<p align="right"><a href="#top">Go 🔝</a></p>

# 3. Svelte Basics

- In Svelte, an application is composed from one or more components.
- File svelte berformat `.svelte`
- Isi file svelte terdiri dari 3 tag utama, yaitu script, html, dan style

```html
<script></script>
<div></div>
<style></style>
```

- File main.js berfungsi sama seperti main.jsx pada reactjs
- Syntax variable/data:

```html
<script>
  let name = "world";
</script>
<h1>Hello {name}!</h1>
```

- Inside the curly braces, we can put any JavaScript we want. Try changing `name` to `name.toUpperCase()`
- Syntax onClick/function:

```html
<script>
  let count = 0;
  const incrementCount = () => (count += 1);
</script>

<button on:click="{incrementCount}">
  Clicked {count} {count === 1 ? "time" : "times"}
</button>
```

- Pemanggilan function pada on:click atau sejenisnya tidak perlu menambahkan kurung `()` karena akan menyebabkan dipanggil otomatis di awal.

<p align="right"><a href="#top">Go 🔝</a></p>

# 4. User input & data binding

- Data binding artinya merujuk kepada variable dan tampilan data yang syncron
- Contoh data binding pada input:

```html
<script>
  let beltColor = "black";
  const changeColor = () => {
    beltColor = "orange";
  };
  const handleInput = (e) => {
    beltColor = e.target.value;
  };
</script>
<main>
  <p style="color: {beltColor};">{beltColor} Color</p>
  <button on:click="{changeColor}">Change beltColor</button>
  <input type="text" on:input="{handleInput}" value="{beltColor}" />
</main>
```

- Data binding pada input dapat dipersingkat menggunakan `bind:value`

```html
<input type="text" bind:value="{beltColor}" />
```
