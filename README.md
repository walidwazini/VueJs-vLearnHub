# vlearnhub-1

- Demo project for Vue3 and Tailwindcss

### Setup Tailwindcss

1. Install tailwindcss, etc..

```
 npm install  tailwindcss@latest postcss@latest autoprefixer@latest
```

2.  Generate configuration files

```
npx tailwindcss init -p
```

3. Configure `tailwind.config.js`, paste the given code into it

```
  purge: ['./index.html', './src/**/*.{vue,js,ts,jsx,tsx}'],

```

4. Create `./src/index.css/`

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
