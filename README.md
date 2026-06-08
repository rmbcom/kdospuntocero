# Buzzer con GitHub Pages + Firebase

Esta version no usa Apps Script ni Google Sheets.

- `index.html`: app de participante, pensada para GitHub Pages.
- `moderador.html`: pantalla del moderador.
- `database.rules.json`: reglas simples para probar rapido.

## Paso 1: Crear Firebase

1. Entra en `https://console.firebase.google.com/`.
2. Crea un proyecto.
3. En el proyecto, crea una app web.
4. Copia la configuracion `firebaseConfig`.
5. Ve a `Realtime Database`.
6. Crea una base de datos.
7. Elige una region cercana.
8. Empieza en modo prueba o pega las reglas de `database.rules.json`.

## Paso 2: Pegar configuracion

En `index.html` y `moderador.html`, reemplaza:

```js
const firebaseConfig = {
  apiKey: "PEGA_AQUI_TU_API_KEY",
  authDomain: "PEGA_AQUI_TU_AUTH_DOMAIN",
  databaseURL: "PEGA_AQUI_TU_DATABASE_URL",
  projectId: "PEGA_AQUI_TU_PROJECT_ID",
  storageBucket: "PEGA_AQUI_TU_STORAGE_BUCKET",
  messagingSenderId: "PEGA_AQUI_TU_MESSAGING_SENDER_ID",
  appId: "PEGA_AQUI_TU_APP_ID"
};
```

por la configuracion real que te da Firebase.

## Paso 3: Publicar participante en GitHub Pages

Sube `index.html` a la raiz de tu repositorio `buzzer-concurso`.

La URL sera algo como:

```text
https://rmbcom.github.io/buzzer-concurso/
```

## Paso 4: Usar el moderador

Puedes abrir `moderador.html` localmente en el ordenador del presentador, o subirlo tambien a GitHub con otro nombre:

```text
https://rmbcom.github.io/buzzer-concurso/moderador.html
```

Pulsa `Activar sonido` antes de empezar.

## Nota de seguridad

Las reglas incluidas son abiertas para ir rapido. Para un uso cerrado, conviene anadir autenticacion anonima o limitar escrituras por sala.
