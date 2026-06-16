# Tablas

## Qué son, para qué sirven y para qué no sirven las tablas

Una tabla es un recurso estructural que organiza datos en filas y columnas. Su objetivo es mostrar relaciones entre datos, facilitando su comparación o la consulta de un valor específico.

Las tablas permiten a las personas comprender patrones, correlaciones o jerarquías en datos numéricos, textuales o de otro tipo. Son especialmente útiles en contextos como informes, estudios estadísticos, catálogos de productos o comparativas técnicas.

Las tablas no deben usarse nunca únicamente como herramienta de diseño o maquetación visual. Es decir, no se deberían crear tablas solo para ubicar elementos en distintas posiciones de la página o para simular un *layout*. Para esos casos, lo adecuado es utilizar CSS Grid Layout, Flexbox o alguna otra técnica más tradicional.

## Características de una tabla

- Muestra datos tabulares y nunca otros tipos de valores.
- Se distingue claramente, tanto de forma visual como semántica, qué filas y celdas funcionan como encabezados.
- Se distinguen claramente los límites de cada celda, fila y columna, así como los de la propia tabla.

## Utilidad, uso previsto y consideraciones de diseño

Las tablas son especialmente útiles para:

- Representar colecciones de datos de forma ordenada.
- Mostrar comparativas de datos.
- Facilitar la consulta rápida de un dato específico.

Se deben evitar o replantear cuando:

- El contenido es lineal y no necesita estructuras tabulares. Es decir, puede resolverse con una lista o una aproximación más narrativa.

Ten en cuenta que:

- Las tablas demasiado grandes pueden resultar muy complejas de navegar, especialmente para usuarios de lectores de pantalla y magnificadores de texto.
- En el actual contexto multidispositivo, se debe garantizar su adecuación a diferentes tamaños y orientaciones de pantalla.

## Requisitos de accesibilidad

- Toda tabla requiere un título o descripción específico que contemple su propósito, implementado mediante el elemento `<caption>`.
- Las celdas que funcionan como encabezados deben marcarse con el elemento `<th>` e indicarse su relación con filas o columnas mediante el atributo `scope`.
- Los elementos `<thead>` y `<tbody>` permiten agrupar las filas de encabezado y del cuerpo, respectivamente.
- En tablas con encabezados múltiples, es posible utilizar las parejas de atributos `headers` e `id` para asociar los datos a sus encabezados.
- Por lo que respecta a los números, tipográficamente hablando pueden ser proporcionales —con ancho variable— o tabulares —con ancho fijo, es decir, que ocupan el mismo espacio—. Los números tabulares están pensados para el trabajo con datos. El hecho de ocupar el mismo ancho hace que con los números tabulares resulte más fácil el reconocimiento de los números y sus posiciones, o procesos como realizar comparaciones entre valores.

Procura alinear a la derecha los valores numéricos para facilitar su lectura y comparación.

### Criterios de conformidad WCAG relacionados

- 1.3.1: Información y relaciones (nivel A).
- 2.1.1: Teclado (nivel A).

## Contenido de esta carpeta
- `tabla-encabezado-horizontal`
- `tabla-encabezado-vertical`
- `tabla-con-scope-aria`
- `tabla-con-dos-encabezados`
- `tabla-con-encabezados-irregulares`

## Artículo relacionado

[a11y tips #3: tablas accesibles](https://www.rubenalcaraz.es/pinakes/accesibilidad/a11y-tips-3-tablas-accessibles/)
