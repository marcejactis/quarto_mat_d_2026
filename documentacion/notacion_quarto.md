# Notación utilizada en el proyecto

## Div y Span, estructuras base
En quarto, se trabaja mucho con:
- divs: Se abren y cierran con `:::`
- spans: Se abren y cierran con corchetes `[]`

Ambos pueden recibir parámetros que se especifican entre llaves:
```
::: {#id .clase param1="true"}
Contenido del div.
:::
```

o,
```
[Contenido del span.]{#id .clase param1="true"}
```

Los *id's* y las *clases* tienen distintos efectos sobre el bloque que contiene dentro contenido. Por ejemplo:
```
# Título sin número {.unnumbered}

A continuación una ecuación que se enumera automáticamente. Esto sucede gracias al id que comienza con "#eq-".
$$
\cos(\theta) = \frac{a}{c}.
$$ {#eq-coseno}

::: {.callout}
Esto es un bloque formateado con una clase predefinida por Quarto.
:::
```

## Bloques resaltados
De esta manera se crean los bloques resaltados que se pueden hallar en el apunte. A continuación se deja como sugerencia la notación utilizada:
- `.callout-tip` + 📝: Ejercicios.
- `.callout-tip` + ⚙️: Desafíos.
- `.callout-tip`: Diferencia entre una cosa y otra que se usan para mas o menos lo mismo.
- `.callout-note`: Datos secundarios al tema, o muy básicos, pero relevantes.
- `.callout-warning`: Datos importantes.
- `.callout-important`: Advertencias, consejos que evitan problemas.


## Entornos matemáticos
Quarto permite crear entornos matemáticos para enunciados como teoremas, definiciones, ejemplos, ejercicios etc. Para ello se utiliza un bloque con la siguiente sintaxis:
```
:::{#entorno-etiqueta}
Texto del enunciado
:::
```

donde entorno es el tipo de entorno, que puede ser `thm` para teoremas, `cor` para corolarios, `prp` para proposiciones, `def` para definiciones, `exm` para ejemplos, `exr` para ejercicios, `sol` o `rem` para observaciones. Junto al entorno hay que añadir una etiqueta con un identificador único para poder referenciarlo en el texto del documento.


## Texto a 2 columnas
Se implementó una clase estilada con CSS llamada `grid-2col` que debe utilizarse de la siguiente forma:

```
:::: {.grid-2col}
::: {}
**Buenos nombres:**

*bloque de código*
:::

::: {}
**Nombres inválidos:**

*bloque de código*
:::
::::
```

## Cómo centrar un div? La eterna pregunta
Para facilitar esta tarea, se armó una clase "center" que se encarga de centrar el bloque. A continuación, un par de ejemplos de uso.

Con spans:
```
[**¿qué hace falta para poder asegurar que $g$ tiene un punto fijo en un intervalo $[a, b]$?**]{.center}
```

Con divs:
```
::: {.center}
**¿cómo podría esto ayudarnos a resolver una ecuación no lineal como $f(x)=0$?**
:::
```


# Referencias
https://quarto.org/docs/guide/

https://aprendeconalf.es/quarto-textos-cientificos/#entornos-matem%C3%A1ticos

https://r-wasm.github.io/quarto-live/getting_started/editor.html

https://www.datanovia.com/es/guide/tools/quarto/figures.html

https://getbootstrap.com/docs/5.1/layout/css-grid/
