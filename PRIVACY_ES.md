# Política de privacidad de sName2Date

Actualizado: 2026-09-24

## Resumen

sName2Date **no** recopila, almacena ni transmite datos personales. La app funciona
exclusivamente en tu Mac y no establece ninguna conexión a internet.

## Qué datos procesa la app

sName2Date lee los archivos que tú le entregas expresamente, ya sea seleccionándolos en el
diálogo de apertura o arrastrándolos a la ventana. Se leen el nombre del archivo y sus
metadatos; se escribe la fecha de captura exactamente en esos archivos.

Si lo deseas, la app además renombra esos archivos (desactivado de fábrica). También ajusta
su fecha de creación y de modificación (activado de fábrica, se puede desactivar en
Ajustes). En los archivos que no pueden contener una fecha de captura —por ejemplo, PDF o
texto—, ajusta en su lugar siempre solo esas dos fechas.

Si la casilla **Escribir la fecha en el archivo** está desactivada, la app **no abre ni un
solo archivo**: lee únicamente el nombre y modifica únicamente el nombre y, si está
configurado, la fecha de creación y de modificación. El contenido no se lee ni se escribe.

Sin tu selección, la app no accede a ningún archivo. macOS lo impone mediante el aislamiento
de apps (sandbox).

Si la app recorre una carpeta en la que está la carpeta «Música», macOS puede preguntar si
puede acceder a «Multimedia y Apple Music». La app no lee ni tu biblioteca ni tu historial
de reproducción. Allí, como en todas partes, trabaja solo con archivos y escribe la fecha en
archivos de audio y vídeo cuyo nombre lleva una.

## Qué guarda la app en tu Mac

- **Los ajustes**, en un archivo `config.json` dentro de la carpeta protegida de la app.
- **Un registro de diagnóstico**, en la misma zona, que se borra automáticamente al cabo de
  siete días. Contiene momentos y cantidades de operaciones. Puedes guardarlo y enviarlo
  desde Ajustes → Diagnóstico; por lo demás, no sale de tu Mac.
- **Las rutas de las carpetas que has autorizado**, junto con el permiso de macOS para
  volver a abrirlas en el siguiente arranque. Solo así la app no tiene que preguntar cada
  vez. La lista contiene rutas de carpetas, no contenidos de archivos, y el botón
  «Seleccionar carpeta» te la muestra.

Todo ello se elimina junto con la app cuando la borras.

**Junto a tus archivos, la app solo crea algo en un caso:** si un archivo de foto, vídeo o
audio no puede contener por sí mismo la fecha de captura (por ejemplo, HEIF, WebP o AVI), la
app la escribe en un archivo acompañante con el mismo nombre y la extensión `.xmp`, que
muchos programas de fotos también leen. ⌘Z lo deshace. Junto a otros archivos, por ejemplo
PDF o texto, nunca se crea ninguno. Si allí ya hay un archivo acompañante —procedente
entonces de otro programa de imagen—, su fecha de captura se actualiza también, para que el
archivo y su acompañante no digan cosas distintas. Lo que la app no entiende dentro de él
queda intacto.

## Sin cesión de datos, sin analítica

No hay publicidad, ni servicios de analítica, ni informes de fallos a terceros, ni cuentas.

## Contacto

Andreas Heiligtag · SwiftAppsBavaria@gmx.net
