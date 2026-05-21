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





# Referencias
https://quarto.org/docs/guide/

https://aprendeconalf.es/quarto-textos-cientificos/#entornos-matem%C3%A1ticos

https://r-wasm.github.io/quarto-live/getting_started/editor.html

https://www.datanovia.com/es/guide/tools/quarto/figures.html
