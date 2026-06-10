# Pseudokahoot v3 con Firebase

Aplicacion tipo Kahoot con estetica hacker/Matrix y Firebase Realtime Database.

Archivos:

- `index.html`: app de participantes.
- `moderador.html`: pantalla del moderador.
- `cargador.html`: app para cargar preguntas con imagen opcional.
- `questions.js`: banco de preguntas local de respaldo.
- `database.rules.json`: reglas simples para probar rapido.

## URLs si lo subes a GitHub Pages

Participantes:

```text
https://TU_USUARIO.github.io/TU_REPO/
```

Moderador:

```text
https://TU_USUARIO.github.io/TU_REPO/moderador.html
```

Cargador de preguntas:

```text
https://TU_USUARIO.github.io/TU_REPO/cargador.html
```

## Como usar el cargador

1. Abre `cargador.html`.
2. Escribe la pregunta.
3. Escribe la respuesta correcta.
4. Escribe tres respuestas falsas.
5. Opcionalmente, sube una imagen.
6. Pulsa **Anadir pregunta**.
7. Repite con todas las preguntas.
8. Pulsa **Publicar banco**.
9. Abre `moderador.html` e inicia partida.

El banco se guarda en Firebase en:

```text
rooms/principal/questionBank
```

## Imagenes

El cargador reduce las imagenes a un maximo aproximado de 900 px y las guarda como base64 dentro de Firebase.

Para clase o pruebas funciona bien. Para bancos enormes o muchas imagenes pesadas, convendria usar Firebase Storage o URLs externas.

## Banco de respaldo

Si no hay preguntas publicadas en Firebase, el moderador usa `questions.js`.

Tambien puedes usar el boton **Descargar questions.js** del cargador para generar un archivo de preguntas y sustituir manualmente el `questions.js` del repositorio.

## Firebase

La app usa:

```text
rooms/principal
```

Campos importantes:

- `participants`
- `currentQuestion`
- `answers`
- `questionBank`
- `status`

## Seguridad

Las reglas incluidas son abiertas para ir rapido. Cualquiera con acceso a las URLs podria leer o escribir datos. Para uso cerrado haria falta Firebase Authentication y reglas con roles.
