# O REPOSITORIO AXON - Guía de Instalación y Despliegue

Este proyecto es una aplicación educativa moderna construida con **React**, **Vite**, **TypeScript** y **Tailwind CSS**, con integración de **Supabase** para backend y bases de datos.

## Requisitos Previos

- **Node.js**: v18 o superior
- **npm** o **pnpm**: Gestor de paquetes
- **Git**: Para control de versiones
- Cuenta de **Supabase** (opcional, para funcionalidades de backend)

## Instalación Local

### 1. Clonar el Repositorio

```bash
git clone https://github.com/Matraca130/O-REPOSITORIO-AXON.git
cd O-REPOSITORIO-AXON
```

### 2. Instalar Dependencias

Usando npm:
```bash
npm install
```

O usando pnpm (recomendado para mejor rendimiento):
```bash
pnpm install
```

### 3. Configurar Variables de Entorno

Copia el archivo `.env.example` a `.env.local` y completa los valores:

```bash
cp .env.example .env.local
```

Edita `.env.local` con tus credenciales de Supabase y otras configuraciones necesarias.

### 4. Ejecutar en Desarrollo

```bash
npm run dev
```

La aplicación estará disponible en `http://localhost:5173` (o el puerto que Vite asigne).

## Construcción para Producción

### Build Local

```bash
npm run build
```

Esto generará la carpeta `dist/` con los archivos optimizados para producción.

### Previsualizar Build Local

```bash
npm run preview
```

## Despliegue en Vercel

### Método 1: Mediante GitHub (Recomendado)

1. **Conectar Repositorio a Vercel**
   - Ve a [vercel.com](https://vercel.com)
   - Inicia sesión con tu cuenta GitHub
   - Haz clic en "New Project"
   - Selecciona este repositorio

2. **Configurar Variables de Entorno**
   - En la configuración del proyecto, ve a "Settings" → "Environment Variables"
   - Añade las siguientes variables:
     - `VITE_SUPABASE_URL`
     - `VITE_SUPABASE_ANON_KEY`
     - `VITE_API_URL` (si es necesario)

3. **Desplegar**
   - Vercel detectará automáticamente que es un proyecto Vite
   - Haz clic en "Deploy"
   - El despliegue se completará automáticamente

### Método 2: Mediante CLI de Vercel

```bash
# Instalar Vercel CLI (si no lo tienes)
npm install -g vercel

# Desplegar
vercel
```

Sigue las instrucciones interactivas para completar el despliegue.

## Estructura del Proyecto

```
O-REPOSITORIO-AXON/
├── src/
│   ├── app/
│   │   ├── components/        # Componentes React reutilizables
│   │   ├── context/           # Contextos de React (estado global)
│   │   ├── design-system/     # Sistema de diseño (colores, tipografía, etc.)
│   │   ├── hooks/             # Hooks personalizados
│   │   ├── lib/               # Utilidades y librerías
│   │   ├── services/          # Servicios de API
│   │   ├── types/             # Tipos TypeScript
│   │   ├── routes/            # Definiciones de rutas
│   │   ├── data/              # Datos estáticos
│   │   └── App.tsx            # Componente principal
│   ├── styles/                # Estilos CSS globales
│   └── main.tsx               # Punto de entrada
├── supabase/
│   └── functions/             # Funciones serverless de Supabase
├── utils/                     # Utilidades generales
├── index.html                 # HTML principal
├── vite.config.ts             # Configuración de Vite
├── tailwind.config.js         # Configuración de Tailwind CSS
├── postcss.config.mjs         # Configuración de PostCSS
├── package.json               # Dependencias del proyecto
├── vercel.json                # Configuración de Vercel
├── .env.example               # Plantilla de variables de entorno
├── .gitignore                 # Archivos ignorados por Git
└── README.md                  # Este archivo
```

## Scripts Disponibles

- `npm run dev` - Inicia el servidor de desarrollo
- `npm run build` - Construye la aplicación para producción
- `npm run preview` - Previsualiza el build de producción localmente

## Características Principales

- ✅ **Autenticación**: Sistema de autenticación con Supabase
- ✅ **Flashcards**: Motor de flashcards con repetición espaciada
- ✅ **Anotaciones**: Sistema de anotaciones de texto
- ✅ **Múltiples Roles**: Soporte para estudiantes, profesores y administradores
- ✅ **Diseño Responsivo**: Interfaz adaptable a cualquier dispositivo
- ✅ **Sistema de Diseño**: Componentes UI consistentes y reutilizables
- ✅ **Integración con IA**: Generación de flashcards con IA

## Solución de Problemas

### Error: "Cannot find module '@'"
Asegúrate de que el alias `@` está configurado correctamente en `vite.config.ts`.

### Error: "VITE_SUPABASE_URL is not defined"
Verifica que las variables de entorno estén configuradas en `.env.local`.

### Build falla en Vercel
- Verifica que todas las variables de entorno estén configuradas en Vercel
- Asegúrate de que la versión de Node.js sea compatible (v18+)
- Revisa los logs de despliegue en Vercel para más detalles

## Contribución

Para contribuir al proyecto:

1. Crea una rama para tu feature: `git checkout -b feature/mi-feature`
2. Realiza tus cambios y haz commit: `git commit -m "feat: descripción del cambio"`
3. Sube la rama: `git push origin feature/mi-feature`
4. Abre un Pull Request

## Licencia

Este proyecto está bajo licencia privada. Ver `LICENSE` para más detalles.

## Soporte

Para reportar problemas o sugerencias, abre un issue en el repositorio de GitHub.

---

**Última actualización**: Febrero 2026
