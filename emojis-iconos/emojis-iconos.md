# Emojis e iconos accesibles

Los emojis y los iconos forman parte habitual de la comunicación digital, sobre todo en dispositivos móviles. Se utilizan para expresar emociones, reforzar el significado de un mensaje, identificar acciones o reducir el espacio ocupado por determinados controles. Los encontramos en redes sociales, aplicaciones móviles, sistemas de navegación, formularios y prácticamente cualquier tipo de sitio web.

Aunque visualmente pueden parecer pequeñas imágenes, su implementación técnica es muy diversa. Los emojis suelen ser caracteres Unicode, mientras que los iconos pueden proceder de ficheros SVG, bibliotecas de fuentes, imágenes o reglas CSS. Esta diversidad obliga a adoptar estrategias diferentes para que su significado también esté disponible para los usuarios de lectores de pantalla.

## Qué son los emojis y los iconos

Un emoji es un carácter gráfico utilizado para representar una emoción, un objeto, una acción o una idea. A diferencia de los emoticonos, construidos mediante combinaciones de signos como `:-)` o `;)`, los emojis son caracteres con una denominación predefinida que los lectores de pantalla pueden anunciar.

Esta denominación no siempre coincide con la intención comunicativa de quien ha utilizado el emoji. Por ejemplo, el símbolo 🙏 puede emplearse para expresar agradecimiento, pedir algo o representar una oración, pero un lector de pantalla puede anunciarlo como «manos juntas».

Los iconos, por su parte, son símbolos visuales que representan objetos, conceptos o acciones. Una lupa suele asociarse con una búsqueda; una rueda dentada, con la configuración; y una papelera, con la eliminación de un elemento. Sin embargo, su significado depende del contexto y no siempre resulta inequívoco.

## Por qué necesitan una alternativa textual

Los lectores de pantalla suelen anunciar los emojis mediante el nombre asignado por Unicode, el sistema operativo o la ayuda técnica utilizada. El resultado concreto puede variar entre dispositivos, navegadores, idiomas y lectores de pantalla.

Cuando el significado de una frase depende exclusivamente del emoji, puede producirse una desconexión entre la intención del autor y la información que recibe el usuario. También pueden resultar problemáticas las secuencias largas de emojis, ya que el lector de pantalla anunciará cada uno de ellos y alargará innecesariamente el mensaje.

Los iconos presentan un problema similar. Un botón que contiene únicamente una imagen de una lupa puede resultar evidente visualmente, pero, si no dispone de un nombre accesible, un lector de pantalla podría anunciar solamente «botón». Los controles interactivos deben contar con un nombre que permita identificar su finalidad.

Además, no conviene utilizar como alternativa textual una simple descripción de la forma del icono. El nombre accesible debe comunicar la acción que realizará el control. Por ejemplo:

- «Buscar», en lugar de «Lupa».
- «Eliminar documento», en lugar de «Papelera».
- «Añadir a favoritos», en lugar de «Corazón».
- «Abrir configuración», en lugar de «Rueda dentada».

## Consideraciones de diseño

- Siempre que sea posible, acompaña los iconos con una etiqueta textual visible. Esta solución beneficia a los usuarios de lectores de pantalla, pero también a quienes no conocen el significado del símbolo, presentan dificultades cognitivas o utilizan la interfaz por primera vez.
- No asumas que un icono posee un significado universal. Un corazón puede servir para indicar que algo gusta, guardarlo como favorito o incorporarlo a una lista de deseos. La etiqueta debe describir la función específica que desempeña en cada interfaz.

En el caso de los emojis:

- Evita utilizarlos como único medio para transmitir información importante.
- Limita las repeticiones y las cadenas largas.
- Colócalos preferentemente al final de las frases para que no interrumpan su lectura.
- Expresa mediante texto cualquier advertencia, estado o emoción importante o necesaria para comprender el mensaje.
- Ocúltalos a las ayudas técnicas cuando sean meramente decorativos o repitan información previamente expresada.

## Requisitos de accesibilidad

Los emojis e iconos deben implementarse de acuerdo con su función:

- Los elementos decorativos deben excluirse del árbol de accesibilidad mediante `aria-hidden="true"`.
- Los iconos acompañados de una etiqueta visible deben ocultarse a los lectores de pantalla para evitar anuncios redundantes.
- Los botones formados únicamente por un icono deben recibir un nombre accesible mediante texto oculto, `aria-label` o `aria-labelledby`.
- Los emojis informativos que no disponen de texto equivalente pueden agruparse mediante `role="img"` y recibir una alternativa con `aria-label`.
- El nombre accesible debe describir el significado o la acción y no únicamente la apariencia del símbolo.
- No debe aplicarse `aria-hidden="true"` a elementos interactivos o que puedan recibir el foco. Este atributo elimina el elemento y todos sus descendientes del árbol de accesibilidad.

## Código HTML y CSS

### Emoji decorativo o redundante

Cuando el texto ya transmite toda la información necesaria, el emoji puede ocultarse a los lectores de pantalla. En este caso, el lector de pantalla anunciará «El formulario se ha enviado correctamente» y «Novedades», respectivamente, sin añadir el nombre del emoji.

```html
<p>
  <span aria-hidden="true">✅</span>
  El formulario se ha enviado correctamente.
</p>
```

```html
<h2>
  Novedades
  <span aria-hidden="true">✨</span>
</h2>
```

### Emoji con significado propio

Cuando un emoji transmite información que no aparece en el texto, se le puede proporcionar una alternativa mediante `role="img"` y `aria-label`:

```html
<p>
  Estado:
  <span role="img" aria-label="Tarea completada">✅</span>
</p>
```

El atributo `role="img"` permite presentar el carácter como una unidad gráfica, mientras que `aria-label` sustituye su denominación predeterminada por una alternativa ajustada al contexto. Esta posibilidad aparece recogida en las técnicas de las WCAG para emojis, emoticonos y arte ASCII.

No obstante, cuando el significado puede incorporarse directamente al texto, la segunda opción —icono acompañado de texto visible— es una solución más robusta:

```html
<p>
  Estado: tarea completada
  <span aria-hidden="true">✅</span>
</p>
```

### Icono acompañado de texto visible

La opción preferible consiste en incluir una etiqueta textual visible y ocultar el icono a las ayudas técnicas. En este caso, el texto situado dentro del botón proporciona su nombre accesible. Por otro lado, el SVG se oculta para impedir que el lector de pantalla anuncie información redundante.

```html
<button type="button">
  <svg
    aria-hidden="true"
    focusable="false"
    width="16"
    height="16"
    viewBox="0 0 16 16"
  >
    <!-- Trazados del icono -->
  </svg>

  Configuración
</button>
```

La misma estrategia puede aplicarse a un icono procedente de una biblioteca de fuentes.

```html
<a href="/favoritos">
  <i class="fa-solid fa-heart" aria-hidden="true"></i>
  Mis favoritos
</a>
```

### Botón formado únicamente por un icono

Cuando el diseño requiere utilizar un botón sin texto visible, debe proporcionarse un nombre accesible. El atributo `aria-label` se aplica al botón y no al icono. De esta manera, el lector de pantalla anunciará algo como «Buscar, botón», en lugar de una combinación innecesaria como «Buscar, imagen, botón».

```html
<button type="button" aria-label="Buscar">
  <svg
    aria-hidden="true"
    focusable="false"
    width="16"
    height="16"
    viewBox="0 0 16 16"
  >
    <!-- Trazados del icono -->
  </svg>
</button>
```

### Iconos puramente decorativos

Los iconos que no transmiten información y no forman parte de un control deben ocultarse. No es necesario proporcionar un nombre accesible a un elemento que únicamente cumple una función estética y cuya eliminación no altera la comprensión del contenido.

```html
<p>
  <svg aria-hidden="true" focusable="false">
    <!-- Icono decorativo -->
  </svg>

  Descubre nuestras últimas publicaciones.
</p>
```


## Artículo relacionado

[a11y tips #5: emojis e iconos accesibles](https://www.rubenalcaraz.es/pinakes/accesibilidad/a11y-tips-5-emojis-iconos-accesibles/)
