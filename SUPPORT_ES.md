# Ayuda de sName2Date

## Qué hace la app

sName2Date busca una fecha en el nombre del archivo y la escribe como fecha de captura en el
archivo de imagen, de vídeo o de audio. Si todavía no hay ninguna fecha de captura, se crea.

En la parte superior de la ventana hay para ello dos casillas, que no se excluyen entre sí:

| | |
|---|---|
| **Escribir la fecha en el archivo** | pone la fecha como fecha de captura dentro del propio archivo — la tarea principal de la app |
| **Convertir los nombres de archivo** | pone el nombre en la escritura ISO, para **cualquier** tipo de archivo |

Las dos juntas son el caso normal. Si solo está marcada la segunda, la app no abre ningún
archivo y solo cambia el nombre.

## Primeros pasos

1. Elige el archivo con «Seleccionar archivo…» o arrástralo a la ventana. La versión completa
   acepta también carpetas enteras con sus subcarpetas.
2. La lista muestra, para cada archivo, la fecha reconocida y, si existe, la fecha de captura
   ya establecida.
3. «Escribir fecha» lleva a cabo el cambio.

## Preguntas frecuentes

**En un archivo pone «No se encontró ninguna fecha en el nombre».**
El nombre no contiene ninguna indicación de fecha reconocible. Se reconocen, entre otros,
`2024-01-15 10-30-00`, `IMG_20240115_103000`, `2024-01-15`, `2024 01 15`, `2024_01_15`,
`15.01.2024`, `15-01-2024`, `15.01.24`, así como nombres de mes escritos con letra, como
`15 ene. 2024`, `15 marzo 2024` o `January 15 2024`. También se leen `2016 04` y `04-2016`:
entonces vale el primero del mes, y la línea lo indica.

La app reconoce los nombres de mes en el idioma de tu sistema y en inglés. Las
transcripciones que sustituyen letras acentuadas no se reconocen (por ejemplo, en alemán,
`15 Maerz 2024` en lugar de `15 März 2024`); en esos casos, introduce la fecha a mano a la
derecha de la línea.

**Una fecha se lee con el día equivocado.**
El 3 de abril se escribe en español `3/4` y en inglés `4/3`: las mismas dos cifras con el
significado invertido. En `15-03-2024` eso no importa, porque no existe un mes 15. Solo
cuando ambas cifras pueden pasar por mes (`03-05-2024`) hay que decidir: entonces aparece
sobre la lista una barra naranja con ambas lecturas para elegir, y las líneas afectadas
quedan señaladas. De fábrica se usa la escritura de tu región del sistema.

**El nombre contiene dos fechas.**
Gana la primera: en `IMG_20240115_editado_2019-03-02`, la toma, no la anotación posterior.
Una indicación con hora tiene siempre preferencia sobre una sin hora.

**El nombre solo contiene una fecha, sin hora.**
Entonces se supone una hora: de fábrica, las 12 del mediodía. Se puede cambiar en los
ajustes.

**Quiero fechar una foto antigua escaneada.**
Se puede: las fechas introducidas a mano llegan hasta 1826, el año de la fotografía
conservada más antigua.

**¿Pierde calidad mi foto?**
No. Los datos de imagen se conservan sin cambios y un JPEG no se vuelve a comprimir. En los
vídeos, las pistas se pasan tal cual, no se vuelven a codificar.

**¿Qué formatos son compatibles?**
La app escribe la fecha de captura dentro del propio archivo en imágenes (JPEG, PNG, TIFF,
HEIC, GIF), vídeos (MP4, MOV, M4V) y grabaciones de audio (M4A, M4B); entonces la marca de
verificación de la línea es verde.

Pero la lista acepta **cualquier** archivo. Cuando el formato no admite una fecha de captura
(un PDF, por ejemplo, un archivo de texto o una hoja de cálculo), la app establece en su lugar
la fecha de creación y de modificación del archivo; la marca es entonces naranja. Las apps,
los alias y los documentos en formato de paquete no aparecen en la lista.

**En mi archivo HEIF, WebP o AVI, la marca es azul.**
Estos tres formatos no admiten una fecha de captura. Por eso la app la escribe en un
acompañante con el mismo nombre y la extensión `.xmp`, que los programas de fotografía como
Lightroom o digiKam también leen.

Con HEIF, a menudo basta con la extensión: los mismos datos, llamados `.heic`, son otro
formato y entonces sí se escriben dentro del propio archivo.

**Solo quiero ordenar los nombres de archivo, sin tocar los archivos.**
Desactiva arriba en la ventana «Escribir la fecha en el archivo» y activa «Convertir los
nombres de archivo». Entonces la app no abre ningún archivo y solo cambia el nombre y, si está
activado en los ajustes, la fecha de creación y de modificación: `Factura 15.03.2024.pdf` se
convierte en `2024-03-15 12-00-00 Factura.pdf`, y la carpeta se ordena por fecha en el
Finder. Esto vale para cualquier tipo de archivo, también PDF, texto u hojas de cálculo.

Si quieres que la fecha se quede donde estaba dentro del nombre, desactiva «Fecha al
principio».

Renombrar cambia la entrada de la carpeta, y para eso macOS necesita el permiso sobre la
carpeta. Si en la versión completa eliges directamente la carpeta, con eso queda concedido. Si
has elegido archivos sueltos (en sName2Date Lite, siempre), la app pregunta una sola vez por
la carpeta: basta con una carpeta superior, y el permiso sigue valiendo tras reiniciar. En la
versión completa, el botón «Seleccionar carpeta» muestra las últimas utilizadas en un menú.

**Junto a mi archivo hay un archivo con la extensión `.xmp`.**
O bien procede de otro programa (Lightroom y digiKam crean esos acompañantes), o bien lo ha
creado sName2Date porque el formato no admite por sí mismo la fecha de captura (HEIF, WebP,
AVI; la marca es entonces azul). ⌘Z elimina de nuevo un acompañante creado así. La app
actualiza el existente cuando cambia la fecha de captura: de lo contrario, el archivo diría
una cosa y su acompañante otra, y la mayoría de los programas leen primero el acompañante.

**En una carpeta grande, la app pregunta si debe seguir leyendo.**
Carpetas enteras de una vez las lee la versión completa. A partir de
5000 archivos (por ejemplo, con la carpeta de usuario y sus subcarpetas) se detiene y
pregunta. Mientras lee y analiza, muestra un contador y una barra de progreso; solo se puede
escribir cuando la lista está completa. Va más rápido con una carpeta más pequeña o sin
«Incluir subcarpetas».

**¿Puedo deshacer un cambio?**
Sí. ⌘Z deshace una pasada entera: la fecha de captura, la fecha de creación y de
modificación y, si está activado, también el nombre de archivo modificado. ⌘⇧Z la vuelve a
aplicar.

Aun así, un aviso: antes de procesar una colección grande, crea una copia de seguridad.
Deshacer restablece los valores, pero no sustituye a una copia de seguridad.

**El renombrado no funcionó, pero la fecha sí está en el archivo.**
Si se eligió un solo archivo, la app únicamente puede trabajar en ese archivo, no en su
carpeta, y renombrar cambia la entrada de la carpeta. Elige la carpeta en lugar del archivo
suelto, o concede la autorización cuando la app la pida. Una autorización concedida una vez
sigue valiendo tras reiniciar y cubre también todas las subcarpetas.

## ¿Algo va mal?

Ajustes → Diagnóstico → «Guardar registro…» reúne los mensajes de los últimos siete días en
un archivo de texto. Envíalo junto con la descripción del error.

## Contacto

SwiftAppsBavaria · SwiftAppsBavaria@gmx.net
