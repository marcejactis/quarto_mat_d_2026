# Notación utilizada en el proyecto

## Consideraciones sobre entornos latex
Para abrir un entorno matemático *en línea*, procurar hacerlo con signo peso simple pegados a la ecuación; por ejemplo, `$e^{i\pi} + 1 = 0$`.

**Evitar!!**

* `$ \cos(x)$`
* `$ \cos(x) $`
* `$\cos(x) $`

Para abrir un entorno matemático *en bloque*, es menéster abrir y cerrar con doble signo `$`, y escribir la ecuación entre medio de la siguiente manera:
```latex
$$
    \cos^2(x) + \sin^2(x) = 1
$$
```

o, en su defecto:
```latex
$$
\cos^2(x) + \sin^2(x) = 1
$$
```

**Evitar!!**

* `$$\cos^2(x) + \sin^2(x) = 1$$` (en línea)
* `$$ \cos^2(x) + \sin^2(x) = 1 $$` (en línea con espacios)
* ```latex
    $$\cos^2(x) + \sin^2(x) = 1
    $$``` (en bloque, mal escrito)

### Entornos matemáticos especiales
Para trabajar de forma cómoda en quarto, es preferible usar entornos que sean compatibles de usar dentro dentro de un entorno matemático (es decir, entre `$$`), ya que permite la previsualización desde el editor de código (se asume el uso de VS Code).

Cuando se desee escribir ecuaciones alineadas, pero sin numerar, evitar el uso del entorno `align*` dentro de un entorno matemático (eso daría **error**); en su lugar, usar el entorno `aligned` dentro de un entorno matemático:
```latex
$$
\begin{aligned}
    \cos(x) &= \sqrt{1 - \sin^2(x)} \\
    &= \frac{1 + \cos(2x)}{2}
\end{aligned}
$$
```

Cuando se desee escribir un sistema de ecuaciones con una llave detrás, usar el entorno `cases` en combinación con `aligned` dentro de un entorno matemático:
```latex
$$
\begin{cases}
\begin{aligned}
    -K_0 u_{xx} &= Q, \quad 0 \le x \le L, \\
    u(0) &= a, \\
    u(L) &= b.
\end{aligned}
\end{cases}
$$
```



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
Para facilitar esta tarea, se armó una clase `.center` que se encarga de centrar el bloque. A continuación, un par de ejemplos de uso.

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

### Centrar el output de un bloque de código

En principio, el comando `#| fig-align: center` dentro del bloque debería funcionar.
```python
#| fig-align: center

import matplotlib.pyplot as plt

plt.figure()
plt.plot([1,2,3], [4,5,6])
plt.show()
```

Sin embargo, cuando el output no es una figura estática convencional (por ejemplo, una animación), este comando no funciona; en su lugar, se debe usar una clase creada de forma personalizada para este propósito: `.center-output`
````quarto
::: {.center-output}

```{python}
from matplotlib.animation import FuncAnimation

# Animación con FuncAnimation
```

:::
````


# Referencias
https://quarto.org/docs/guide/

https://aprendeconalf.es/quarto-textos-cientificos/#entornos-matem%C3%A1ticos

https://r-wasm.github.io/quarto-live/getting_started/editor.html

https://www.datanovia.com/es/guide/tools/quarto/figures.html

https://getbootstrap.com/docs/5.1/layout/css-grid/
