# Borneo 360°

Plataforma comercial Borneo: dashboard por cliente con gestión de inventario, ventas, vendedores y carga de datos.

## Cómo desplegar a Vercel

### Opción A — Drag & drop (más rápido, sin instalar nada)

1. Entra a https://vercel.com → Login (puedes con tu Google o GitHub)
2. En el dashboard de Vercel, click en "**Add New...**" → "**Project**"
3. Click en "**Browse**" o arrastra esta carpeta completa al área de "Deploy"
4. Vercel detecta automáticamente que es un sitio estático
5. Click "**Deploy**". En 30 segundos tendrás una URL tipo `borneo-360-xyz.vercel.app`

### Opción B — Vercel CLI (si tienes Node instalado)

```bash
# Una sola vez: instalar la CLI
npm install -g vercel

# Desde esta carpeta
cd borneo-360-vercel
vercel login              # primera vez nada más
vercel                    # primer deploy (preview)
vercel --prod             # deploy a producción
```

Te preguntará el nombre del proyecto. Acepta los defaults.

### Opción C — GitHub + Vercel (recomendado para uso continuo)

1. Crea un repo nuevo en GitHub (ej. `borneo-360`)
2. Sube el contenido de esta carpeta:
   ```bash
   git init
   git add .
   git commit -m "Initial deploy"
   git remote add origin git@github.com:tu-usuario/borneo-360.git
   git push -u origin main
   ```
3. En Vercel → "**Add New Project**" → conecta tu cuenta de GitHub → selecciona el repo
4. Cada `git push` desplegará automáticamente

## Configuración del dominio

Una vez desplegado, en Vercel → Project → Settings → Domains, puedes apuntar uno propio (ej. `360.borneo.co`).

## Notas

- Es una **single-page app estática**. Todo el código y los datos viven en `index.html`.
- Los datos custom (uploads de Excel) y usuarios se guardan en `localStorage` del navegador — son por dispositivo.
- Para que varios usuarios compartan datos en tiempo real necesitarías agregar un backend (Supabase, Firebase, o API propia).

## Estructura

```
borneo-360-vercel/
├── index.html       (1.6 MB - app completa)
├── vercel.json      (config Vercel)
├── package.json     (metadata)
└── README.md        (este archivo)
```

