# Dragon Ball Z: Super Gokūden — Totsugeki-hen — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Traducción al **español de España**, hecha **desde la ROM japonesa original**,
de *Dragon Ball Z: Super Gokūden — Totsugeki-hen* (Super Famicom, Bandai,
1995), una aventura conversacional que recorre el manga original desde que Son
Goku y Bulma se conocen hasta la derrota de Piccolo Daimao.

Nunca salió de Japón ni se tradujo al castellano.

La traducción se reparte como **parche**: no incluye el juego. Necesitas tu
propia copia para aplicarlo.

## Qué incluye

| Parte | Estado |
|---|---|
| Guion e interfaz | **6.534 cadenas traducidas** |
| Alfabeto español | **103 glifos nuevos**: minúsculas, á é í ó ú ü ñ, ¡ y ¿ |
| Anchura variable | Fuente proporcional nueva: de 14 a **24 caracteres por línea** |
| Rótulos gráficos | Se conservan en japonés (ver abajo) |

El cartucho original **no tenía minúsculas**: solo mayúsculas de ancho
completo, pensadas para acompañar al japonés. Hubo que dibujar el alfabeto
latino entero, respetando el trazo y el contraste de los glifos originales.

Como el motor escribía con **anchura fija**, el castellano no cabía: 14
caracteres por línea. Se ha añadido al motor de texto una **anchura variable
por glifo**, lo que sube el límite a unos 24 y permite escribir español de
verdad en lugar de telegramas.

## Qué se conserva en japonés, a propósito

- El logotipo **DRAGON BALL Z** y el rótulo del título.
- La línea de copyright original.
- La rejilla de kana de la pantalla de nombres.

Son imagen de marca del juego, y la historia se entiende igual.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia de la **ROM japonesa**. El parche solo funciona con esa
   versión exacta.
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Tamaño | 2.097.152 bytes (2 MB) |
   | MD5 | `8bd89634d1b2205b1e7ef016485c0076` |
   | SHA-1 | `926b861734cdeef9e70cd436be62c73481e7392f` |

   ```bash
   md5sum "Dragon Ball Z - Super Gokuu Den - Totsugeki Hen (Japan).sfc"   # Linux
   md5 "…"                                                                # macOS
   CertUtil -hashfile "…" MD5                                             # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto.
4. Aplícalo con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "original.sfc" parche.xdelta "traducido.sfc"`
5. Comprueba que la ROM resultante tiene **4.194.304 bytes (4 MB)** y estas
   huellas:

   | | |
   |---|---|
   | MD5 | `e95b281f4a81ae88dca204b8450c29c3` |
   | SHA-1 | `6ed4b35d666b4ab665abc21128697235517589bf` |

   El parche `.xdelta` tiene SHA-256 `5dfc565c905059cecb5a2bd1fddacd25fd316885143b8694b8df3f747c3e4f93`.

La ROM traducida **ocupa el doble que la original**. El texto en castellano no
cabía en el cartucho de 2 MB, así que se amplía a 4 MB. Funciona en emuladores
y flashcards; para una reproducción en cartucho físico hay que tenerlo en
cuenta.

## Cómo se ha comprobado

- La ROM japonesa, reconstruida con el mecanismo nuevo pero **sin traducir**,
  da **201 de 201 fotogramas idénticos** a la original. Eso separa los cambios
  del motor de los del idioma.
- Cada cadena volcada se vuelve a codificar y **reproduce sus bytes originales**
  (7.596 de 7.596, sin fallos).
- El parche se aplica sobre una copia limpia y el resultado **reproduce la ROM
  probada byte a byte**.
- La construcción es **un solo comando** desde la ROM limpia, con 201
  comprobaciones de integridad que leen la ROM resultante y fallan si falta
  cualquier parche.
- **Guardar y cargar** comprobado leyendo la SRAM real, con control negativo:
  la partida se guarda, se recupera y los nombres del jugador no se corrompen.

## Límites, dichos claramente

- **No hay una partida completa jugada de principio a fin.** Las comprobaciones
  se han hecho forzando escenas, con rutas dirigidas y leyendo la pantalla.
- **No se ha probado en consola física.**
- La traducción y su revisión **las han hecho modelos de lenguaje**, con
  supervisión y criterio editorial fijados por escrito, pero **no equivalen a
  una revisión humana independiente**.
- **Del capítulo 2 en adelante no se ha revisado jugando.** Faltan por ver 5
  de los 100 rótulos de lugar y 4 escenarios.
- El **menú de título** se conserva en inglés porque así está en el original:
  es diseño del juego, no texto sin traducir.
- La frase de la pantalla de fin de partida es una redacción propia y está
  pendiente de repaso.

## Aviso

Traducción hecha por afición, sin ánimo de lucro y sin relación alguna con Bird
Studio, Shūeisha, Toei Animation ni Bandai. Aquí no se distribuye el juego ni
ninguna parte de él: solo un parche que modifica una copia que ya tengas.

Si eres titular de los derechos y quieres que retire esto, abre una incidencia
y lo hago.
