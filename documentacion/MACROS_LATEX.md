# Macros LaTeX para Cálculo Numérico

Este archivo contiene macros LaTeX comunes que puedes usar en tus capítulos.

## Opción 1: Incluir en cada archivo .qmd que los necesite

Agrega esto al inicio del archivo .qmd (después del YAML header):

```markdown
$$
\newcommand{\R}{\mathbb{R}}
\newcommand{\N}{\mathbb{N}}
\newcommand{\Z}{\mathbb{Z}}
\newcommand{\Q}{\mathbb{Q}}
\newcommand{\C}{\mathbb{C}}
\newcommand{\abs}[1]{\left\vert #1 \right\vert}
\newcommand{\norm}[1]{\left\Vert #1 \right\Vert}
\newcommand{\inner}[2]{\left\langle #1, #2 \right\rangle}
\newcommand{\dd}{\mathop{}\!\mathrm{d}}
\newcommand{\bigO}{\mathcal{O}}
$$
```

## Opción 2: Crear un archivo _macros.tex e incluirlo

1. Crea un archivo `_macros.tex` en la raíz del proyecto con:

```latex
\newcommand{\R}{\mathbb{R}}
\newcommand{\N}{\mathbb{N}}
\newcommand{\Z}{\mathbb{Z}}
\newcommand{\Q}{\mathbb{Q}}
\newcommand{\C}{\mathbb{C}}
\newcommand{\abs}[1]{\left\vert #1 \right\vert}
\newcommand{\norm}[1]{\left\Vert #1 \right\Vert}
\newcommand{\inner}[2]{\left\langle #1, #2 \right\rangle}
\newcommand{\dd}{\mathop{}\!\mathrm{d}}
\newcommand{\bigO}{\mathcal{O}}
```

2. En cada capítulo que lo necesite, incluye:

```markdown
---
title: "Tu Capítulo"
include-in-header:
  - text: |
      $$
      \input{_macros.tex}
      $$
---
```

## Uso de los macros

Una vez definidos, puedes usar:

- `$f: \R \to \R$` para funciones de reales a reales
- `$\norm{x}$` para la norma de un vector
- `$\abs{x}$` para valor absoluto
- `$\inner{x}{y}$` para producto interno
- `$\int_a^b f(x) \dd x$` para integrales con el diferencial bien formateado
- `$\bigO(n^2)$` para notación O grande

## Ejemplos completos

```markdown
Sea $f: \R \to \R$ una función continua en $[a,b]$.

El error de aproximación es $\bigO(h^2)$.

La norma euclídea se define como $\norm{x} = \sqrt{\sum_{i=1}^n x_i^2}$.

El producto interno es $\inner{x}{y} = \sum_{i=1}^n x_i y_i$.

La integral definida: $\int_a^b f(x) \dd x$
```

## Recomendación

Por ahora, usa la **Opción 1** y agrega los macros al inicio de cada capítulo donde los necesites. Es más simple y no causa problemas de renderizado en el índice principal.
