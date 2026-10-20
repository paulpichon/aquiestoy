# aquiestoy.mx

Página de "próximamente" construida con **Vite** + **TypeScript**, gestionada con **pnpm**.

## Requisitos

- Node.js (probado con v24)
- pnpm

## Puesta en marcha

```sh
pnpm install   # instala dependencias
pnpm dev       # servidor de desarrollo en http://localhost:5173
```

## Scripts

| Comando             | Qué hace                                        |
| ------------------- | ----------------------------------------------- |
| `pnpm dev`          | Arranca Vite con hot reload                     |
| `pnpm build`        | Compila (comprueba tipos + genera `dist/`)      |
| `pnpm preview`      | Sirve la build de producción localmente         |
| `pnpm typecheck`    | Solo comprueba tipos con `tsc --noEmit`         |

## Nota sobre PowerShell

`pnpm` funciona con normalidad: PowerShell resuelve el shim `pnpm.CMD` (un batch),
y la política de ejecución solo afecta a los scripts `.ps1`.

En cambio, si usas `npm` y falla con *"la ejecución de scripts está deshabilitada
en este sistema"*, es porque PowerShell prefiere el shim `npm.ps1` (un script) y la
política de ejecución por defecto en Windows es `Restricted`. Tienes dos opciones:

- Usar `npm.cmd` en su lugar:

  ```sh
  npm.cmd install
  npm.cmd run build
  ```

- O habilitar scripts locales para tu usuario (no requiere admin):

  ```powershell
  Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
  ```

## Estructura

```
aquiestoy/
├─ index.html        → markup + metas SEO/Open Graph
├─ public/
│  └─ favicon.svg
└─ src/
   ├─ main.ts        → punto de entrada
   └─ style.css      → estilos
```
