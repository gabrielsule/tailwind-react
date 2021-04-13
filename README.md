### Creación de la aplicación
```bash
npx create-react-app dummy
```

### Instalación de Tailwind y dependencias
```bash
cd dummy

npm i tailwindcss@npm:@tailwindcss/postcss7-compat 

npm i @tailwindcss/postcss7-compat 

npm i postcss@^7 

npm i autoprefixer@^9
```

### Instalación de Craco
```bash
npm install @craco/craco
```

### Creación de craco.config.js (raiz)
```javascript
module.exports = {
  style: {
    postcss: {
      plugins: [
        require('tailwindcss'),
        require('autoprefixer'),
      ],
    },
  },
}
```

### Modificación de package.json
```json
"scripts": {
    "start": "craco start",
    "build": "craco build",
    "test": "craco test",
    "eject": "react-scripts eject"
},
```

### Creación de tailwind.config.js
```bash
npx tailwindcss init --full
```


### Creación de index.css y tailwind.css
> Desde la raíz del proyecto, crear una carpeta denominada **src/styles** y dentro de la misma, creamos los dos archivos css
> En index.css, agregamos el siguiente código
```javascript
@tailwind base;

@tailwind components;

@tailwind utilities
```

### Modificación de package.json
```json
"scripts": {
    "build:style": "tailwind build src/styles/index.css -o src/styles/tailwind.css",
    "start": "craco start",
    "build": "craco build",
    "test": "craco test",
    "eject": "react-scripts eject"
  },
```

### Modificación de index.js
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import './styles/tailwind.css';
import App from './App';
```

### Compilar la aplicación
```bash
npm run build:style
```

### Probar la aplicación
```bash
npm start
```
[http://localhost:3000](http://localhost:3000)