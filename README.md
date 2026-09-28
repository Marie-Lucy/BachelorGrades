# Mi Control de Notas · UDELAS Ingeniería Biomédica

Página web para llevar el control de calificaciones (5 años, 33/33/34, índice acumulado).

- **Sin configurar nada:** las notas se guardan en el navegador de cada dispositivo.
- **Con Firebase configurado + sesión de Google:** las notas se sincronizan entre todos tus dispositivos.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La aplicación |
| `firebase-config.js` | Datos de tu proyecto de Firebase (lo único que tienes que editar) |
| `firestore.rules` | Reglas de seguridad para pegar en Firebase (solo tú ves tus notas) |

## 1. Publicar en GitHub Pages

1. En GitHub: **New repository** → nombre `notas` → **Public** → Create.
2. **Add file → Upload files** → arrastra los 4 archivos → **Commit changes**.
3. **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main` / `(root)` → **Save**.
4. En 1–2 minutos queda en `https://TU-USUARIO.github.io/notas/`.

## 2. Activar la nube (Firebase, gratis)

1. Entra a <https://console.firebase.google.com> → **Crear proyecto** (puedes desactivar Google Analytics).
2. **Authentication → Comenzar → Método de acceso → Google → Habilitar** → elige tu correo de asistencia → Guardar.
3. **Authentication → Configuración → Dominios autorizados → Agregar dominio** → `TU-USUARIO.github.io`.
4. **Firestore Database → Crear base de datos** → modo *producción* → cualquier ubicación → Crear.
   Luego pestaña **Reglas** → borra lo que hay, pega el contenido de `firestore.rules` → **Publicar**.
5. **⚙️ Configuración del proyecto → Tus apps → icono `</>` (Web)** → ponle un nombre → Registrar (sin Hosting).
   Copia los valores de `firebaseConfig`.
6. En GitHub abre `firebase-config.js` → icono ✏️ → reemplaza los valores → **Commit changes**.

Espera 1 minuto, abre tu página → **☁️ Cuenta y Sincronización → Iniciar sesión con Google**.
En el celular abre el mismo enlace e inicia sesión con **la misma cuenta**.

> La `apiKey` de Firebase para web no es una contraseña: es normal que sea pública. Lo que protege tus notas son las reglas de `firestore.rules`.

## Respaldo

- ⬇️ descarga una copia `.json` de tus notas.
- ⬆️ importa una copia `.json` (sirve para pasar notas de la versión anterior).
