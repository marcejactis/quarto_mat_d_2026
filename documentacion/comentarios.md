# Generales

## Scripts importantes

Creo que sería buena idea incorporar una pestaña, capítulo, sección o alguna forma de acceso directo a los códigos de relevancia en cada sección. Por ejemplo, una forma de acceder rápidamente a los códigos de bisección, newton, etc. del capítulo 2.

## Código en Octave

Creo que podría sumar si, en los scripts importantes, el usuario puede navegar entre la versión en Python y la versión en Octave. Estoy seguro que sería de gran utilidad para los profesores.

No tuve tiempo de incorporarlo, pero no debería presentar mucha dificultad. Para ello, dejaré algunos links con información:

* https://quarto.org/docs/interactive/layout.html#tabset-panel
* https://www.dannygarside.co.uk/blog/Using-Octave-from-RStudio-in-a-Quarto-document-on-Windows/

Ejemplo de uso:

````quarto
::: {.panel-tabset}

## Python

```{python}
f = lambda x: x**2 + 1
print(f(2))
```

## Octave

```{octave}
f = @(x)(x.^2 + 1);
disp(f(2));
```

:::
````

Por otro lado, será necesario modificar el archivo para CI (.github/workflows/publish.yml) agregando lo siguiente:

```yml
- name: Install GNU Octave
        run: |
          sudo apt-get install -y octave
          pip install octave_kernel
```

Yo ya dejé modificado los archivos pertinentes en `styles/` para que se vea bien en ambos, modo oscuro y claro.

# Capítulo 1: Intro Python

Desde la perspectiva de un alumno, actualmente se siente algo caótico y sobrecargado de información.

# Capítulo 2: No Lineales

# Capítulo 3: Interpolación

# Capítulo 4: Integración

# Capítulo 5: PVI

# Capítulo 6: Diferencias Finitas

Encontré en los scripts de difusión porciones de código que parecen graficar con IPython display, supongo que con propósitos didácticos, pero sus lineas de código están comentadas. Creo que esto podría generar confusión en el alumno que, muy probablemente, copie y pegue el script del libro a su computadora.
