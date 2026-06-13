# Paginación y migas de pan

## Qué son y para qué sirven los sistemas de paginación

La paginación es un componente de navegación que permite distribuir un conjunto amplio de resultados entre varias páginas. Se utiliza habitualmente en blogs, catálogos, tiendas en línea, directorios, archivos de noticias, buscadores y otros sitios web que muestran listas extensas de registros.

Su objetivo es facilitar el desplazamiento entre diferentes grupos de resultados sin presentar una cantidad excesiva de información en una sola página.

## Características principales de la paginación

- Puede presentar enlaces numerados que permiten acceder directamente a una página concreta.
- Puede incluir enlaces para avanzar o retroceder mediante las opciones «Anterior» y «Siguiente».
- Puede combinar enlaces numéricos con controles de navegación secuencial.
- La página que se está consultando debe identificarse visual y semánticamente.
- Los controles deben implementarse como enlaces cuando producen un cambio de ubicación.

## Utilidad, uso previsto y consideraciones de diseño

La paginación se acostumbra a utilizar cuando:

- Una lista de resultados es demasiado extensa para mostrarse en una única página.
- Es necesario permitir que los usuarios avancen o retrocedan por bloques de resultados.
- Conviene ofrecer acceso directo a páginas concretas de una colección.

Ten en cuenta que:

- El texto y los elementos gráficos deben presentar suficiente contraste con el fondo.
- El diseño visual debe permitir reconocer claramente los enlaces como elementos interactivos.
- El estado correspondiente a la página actual no debe comunicarse únicamente mediante el color.
- Los enlaces deben disponer de un área de interacción suficientemente amplia.
- El orden de tabulación debe coincidir con el orden visual de los controles.
- Los enlaces «Anterior» y «Siguiente» deben tener nombres comprensibles incluso cuando incorporen iconos o flechas.
- No deben utilizarse elementos `<button>` para enlaces que conducen a otra página. La opción semánticamente adecuada es un elemento `<a>` con un atributo `href`.

## Migas de pan

Las migas de pan, también denominadas hilos de Ariadna o *breadcrumbs*, son un sistema de navegación que muestra la posición de una página dentro de la estructura jerárquica de un sitio web.

Generalmente, presentan una secuencia que comienza en la página de inicio y continúa por las diferentes secciones o niveles hasta llegar a la página actual.

Por ejemplo:

`Inicio > Accesibilidad > Componentes web > Paginación`

## Utilidad, uso previsto y consideraciones de diseño de las migas de pan

Las migas de pan permiten:

- Informar a los usuarios sobre su ubicación dentro del sitio web.
- Comprender la relación jerárquica entre la página actual y sus páginas superiores.
- Regresar rápidamente a una sección o nivel anterior.
- Complementar otros sistemas de navegación, como el menú principal.

Ten en cuenta que:

- Las migas de pan no deben sustituir al sistema de navegación principal.
- Deben reflejar una jerarquía real y coherente.
- El orden de los elementos debe comenzar en el nivel más general y finalizar en la página actual.
- Los separadores visuales entre los elementos no deben generar información redundante para los lectores de pantalla.
- La página actual debe identificarse de forma visual y mediante `aria-current="page"`.

## Requisitos de accesibilidad

### Requisitos comunes

- Utiliza un elemento semántico `<nav>` para agrupar cada sistema de navegación.
- Proporciona a cada bloque `<nav>` un nombre accesible único mediante `aria-label` o `aria-labelledby`.
- No añadas `role="navigation"` a un elemento `<nav>`, ya que su semántica nativa ya define este tipo de región.
- Estructura los enlaces mediante listas HTML.
- Garantiza que todos los enlaces puedan recibir el foco y activarse mediante el teclado.
- Mantén un indicador de foco visible.
- Asegura un contraste suficiente para el texto, los iconos y los indicadores de foco.
- Utiliza textos de enlace o nombres accesibles que describan adecuadamente el destino.

### Paginación

- Utiliza una lista no ordenada `<ul>` para agrupar los controles.
- Implementa los cambios de página mediante enlaces `<a>` con un atributo `href`.
- Etiqueta el bloque de navegación, por ejemplo, con `aria-label="Paginación"`.
- Identifica el enlace correspondiente a la página actual mediante `aria-current="page"`.
- Proporciona nombres accesibles claros a los enlaces anterior y siguiente, por ejemplo, `aria-label="Página anterior"` y `aria-label="Página siguiente"`.
- Cuando los números de página no resulten suficientemente descriptivos, utiliza nombres como `aria-label="Página 3"`.
- Si no existe una página anterior o siguiente, evita crear un enlace sin destino o un control que parezca operativo.

### Migas de pan

- Utiliza una lista ordenada `<ol>` para representar la secuencia jerárquica.
- Etiqueta el bloque de navegación, por ejemplo, con `aria-label="Ruta de navegación"`.
- Identifica la página actual mediante `aria-current="page"`.
- Añade los separadores mediante CSS o escóndelos de las tecnologías de asistencia cuando sean meramente decorativos.
- Evita incluir nombres ambiguos o abreviaturas que dificulten la identificación de cada nivel.

## Criterios de conformidad WCAG relacionados

- 1.3.1: Información y relaciones (nivel A).
- 1.4.3: Contraste mínimo (nivel AA).
- 1.4.11: Contraste no textual (nivel AA).
- 2.1.1: Teclado (nivel A).
- 2.4.4: Propósito de los enlaces en contexto (nivel A).
- 2.4.7: Foco visible (nivel AA).
- 4.1.2: Nombre, función, valor (nivel A).

## Código HTML

En los ejemplos se utilizan los siguientes elementos y atributos:

- `<nav>`: identifica el bloque como una región de navegación.
- `<ul>`: agrupa los enlaces de una paginación.
- `<ol>`: representa el orden jerárquico de unas migas de pan.
- `<li>`: contiene cada uno de los elementos de navegación.
- `<a href="">`: implementa los enlaces que conducen a otras páginas.
- `aria-label`: proporciona un nombre accesible al bloque de navegación o a un enlace cuando su texto visible no resulta suficientemente descriptivo.
- `aria-labelledby`: permite nombrar el bloque de navegación mediante otro elemento de la página.
- `aria-current="page"`: identifica el enlace o elemento que representa la página actual.
- `aria-hidden="true"`: puede utilizarse para ocultar a los lectores de pantalla flechas o separadores puramente decorativos.

La paginación y las migas de pan pueden implementarse con HTML y CSS sin necesidad de JavaScript. Solo se requiere JavaScript cuando la carga de resultados se realiza dinámicamente sin una navegación convencional a otra URL. En ese caso, también debe gestionarse correctamente el foco y comunicarse la actualización del contenido a las tecnologías de asistencia.

## Contenido de esta carpeta

- `paginacion-numerada`: ejemplo de paginación con enlaces numéricos y controles para avanzar y retroceder.
- `paginacion-anterior-siguiente`: ejemplo simplificado basado únicamente en los enlaces «Anterior» y «Siguiente».
- `migas-de-pan`: ejemplo de ruta de navegación jerárquica mediante una lista ordenada.
