# Notas a pie de página

## Qué son y para qué sirven las notas a pie de página

Una nota al pie de página (*footnote*, en inglés) es un recurso textual que ofrece información adicional, aclaratoria o bibliográfica. Su finalidad es permitir que las personas accedan al contenido complementario cuando lo necesiten, sin que este interfiera con la lectura del contenido principal.

## Características de una nota a pie de página

- Referencia contextual clara: debe establecerse un vínculo visible y comprensible entre el marcador en el texto —generalmente un superíndice o un número— y la nota al pie.
- Navegación bidireccional: se debe permitir ir de la referencia en el texto a la nota y volver a la posición original.
- Contenido relevante y conciso: la nota debe ampliar o contextualizar el contenido sin introducir digresiones innecesarias.
- Si bien en documentos ofimáticos aparecen en el pie de la página en la que se invocan, en un sitio web lo más habitual es ubicarlas al final de la página.

## Utilidad, uso previsto y consideraciones de diseño

- Aportan aclaraciones, fuentes o comentarios que enriquecen el contenido sin romper la fluidez de la lectura.
- Se utilizan habitualmente en documentos académicos, libros digitales, artículos extensos o ensayos críticos.

Se acostumbra a utilizar cuando se requiere:

- Incluir referencias bibliográficas sin interrumpir la argumentación principal.
- Aportar comentarios o explicaciones complementarias.

No debe utilizarse cuando:

- El contenido de la nota es esencial para comprender el texto y no debería estar separado.

Ten en cuenta que:

- Si las notas se implementan incorrectamente, pueden romper el flujo de lectura o dificultar el acceso a la información.
- La interacción con la nota no debe implicar acciones complejas que requieran demasiados clics.
- El uso de modales o elementos interactivos poco accesibles puede impedir que algunos usuarios accedan a las notas.

## Requisitos de accesibilidad

- Los superíndices deben incorporar información semántica (`aria-label`) para que los lectores de pantalla puedan anunciar que se trata de una nota al pie, así como otros atributos y roles ARIA adicionales que se muestran más adelante.
- Navegación con teclado: las notas deben poder activarse usando solo el teclado.
- Debe existir un mecanismo claro y accesible para volver desde la nota al punto del texto donde fue invocada.
- Si se presentan en el pie de página o al final del documento, deben estar etiquetadas semánticamente como tal —por ejemplo, dentro de una `<section>` o `<aside>` con el rol adecuado—.

### Criterios de conformidad WCAG relacionados

- 1.3.1: Información y relaciones (nivel A).
- 2.1.1: Teclado (nivel A).
- 2.4.4: Propósito del enlace (nivel A).
- 4.1.2: Nombre, rol, valor (nivel A).

## Artículo relacionado

[a11y tips #2: notas a pie de página accesibles](https://www.rubenalcaraz.es/pinakes/accesibilidad/a11y-tips-2-notas-a-pie-de-pagina/)
