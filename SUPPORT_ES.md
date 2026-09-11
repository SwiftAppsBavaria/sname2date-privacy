# Ayuda de sName2Date

## Qué hace la app

sName2Date busca una fecha en el nombre del archivo y la escribe como fecha de captura en el
archivo de imagen o de vídeo. Si todavía no hay ninguna fecha de captura, se crea.

Para ello, la versión completa tiene **dos modalidades**, conmutables en la parte superior de
la ventana:

| | |
|---|---|
| **Fecha de captura** | escribe la fecha dentro del archivo — la tarea principal de la app |
| **Nombres de archivo** | solo pone el nombre en la escritura ISO, para **cualquier** archivo |

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
En la modalidad *Fecha de captura*: imágenes JPEG, PNG, TIFF, HEIC y GIF; vídeos MP4, MOV y
M4V. En todos ellos, la app escribe la fecha dentro del propio archivo.

En la modalidad *Nombres de archivo* no cuenta **ninguna extensión**: allí solo se cambia el
nombre, y nombre lo tiene todo archivo.

**Mi archivo HEIF, WebP o AVI ni siquiera aparece en la lista.**
Estos tres formatos no admiten una fecha de captura; la app solo podría dejar la fecha al
lado en vez de escribirla dentro, y no está hecha para eso. Por ello se omiten al cargar en
la modalidad *Fecha de captura*; una línea sobre la lista indica cuántos eran.

Renombrarlos sí es posible: para ello cambia a *Nombres de archivo*.

Con HEIF, a menudo basta con la extensión: los mismos datos, llamados `.heic`, son otro
formato y entonces sí se escriben.

**Solo quiero ordenar los nombres de archivo, sin tocar los archivos.**
Cambia arriba en la ventana a *Nombres de archivo*. Entonces la app no abre ningún archivo y
solo cambia el nombre: `Factura 15.03.2024.pdf` se convierte en
`2024-03-15 12-00-00 Factura.pdf`, y la carpeta se ordena por fecha en el Finder. Esto vale
para cualquier tipo de archivo, también PDF, texto u hojas de cálculo.

Si quieres que la fecha se quede donde estaba dentro del nombre, desactiva «Fecha al
principio».

⚠️ En esta modalidad, la app solo acepta **carpetas**, no archivos sueltos. El motivo es el
propio renombrado: cambia la entrada de la carpeta, y para eso macOS necesita el permiso
sobre la carpeta, que surge al seleccionarla tú. Una vez elegida, la app la recuerda; el
botón «Seleccionar carpeta» muestra las últimas utilizadas en un menú.

**Junto a mi archivo hay un archivo con la extensión `.xmp`.**
Procede de otro programa: Lightroom y digiKam crean esos acompañantes. sName2Date no genera
ninguno, pero actualiza el existente cuando cambia la fecha de captura. De lo contrario, el
archivo diría una cosa y su acompañante otra, y la mayoría de los programas leen primero el
acompañante.

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
