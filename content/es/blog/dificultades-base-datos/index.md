---
title: "Dificultades construyendo una base de datos"
description: "Descripción de dificultades técnicas y de planeación para construir una base de datos"
lead: "OpenFormula debe construirse alrededor de las fórmulas pero ¿cómo deberían escribirse las bases de datos?"
date: 2023-06-27T00:44:00+06:00
lastmod: 2023-06-27T00:44:00+06:00
draft: false
weight: 50
images: []
contributors: ["Uri Mtz"]
---

## Hacer una aplicación no es fácil

Cómo se planteó en la primer publicación, construir una aplicación no es sencillo y conlleva de mucha planeación. Para el caso de OpenFormula, se debe construir alrededor de las fórmulas, pero esta tarea no es sencilla, pues las fórmulas tienen un nombre, en algunos casos más de uno o carecen de uno "oficial", por lo que hay que dictaminar reglas para nombrar fórmulas lo cuál requiere de conocer la estructura de la aplicación, la cual se deconoce porque no hay una estructura formada para hacer las bases de datos.

## Dificultades generales

Una fórmula, cómo ya se mencionó, no sólo se compone de la estructura misma, también requiere de un nombre y en ciertas fórmulas del conocer que significan las variables presentes, las unidades que se deben usar y de ser necesario, notas específicas acerca de la fórmula tales cómo excepciones a la regla, etc. Son muchas cosas a tomar en cuenta.

Ignorando momentaneamente las dificultades técnicas que puede conllevar el hacer una base de datos, se debe pensar que se quiere dar al usuario, el nombre de la fórmula, la fórmula, las variables, otros nombres, notas, etc. Pero algunas pueden requerir otros campos o requerir menos, por lo que hay que pensar en la "universalidad" y hablando de este mismo concepto, llega la primer dificultad

### ¿Cómo nombrar las fórmulas?

Algunas fórmulas o ecuaciones populares ya tienen nombres determinados, pero ¿qué sucede con fórmulas más generales? Poniendo cómo ejemplo el nombramiento de una fórmula para calcular el área de un cuadrado, no tiene un nombre "oficial" por lo que puede nombrarse de muchas formas, por dar un par de ejemplos:

- "Cálculo de área de un cuadrado"
- "Fórmula área de un cuadrado"
- "Área de cuadrado"
- "Superficie de un cuadrado"
- "Cálculo de la superficie de un cuadrado"
- "Fórmula superficie de un cuadrado"

Y se pueden hacer más combinaciones, usar sinónimos, etc.

Para poder solucionar este problema se debe escribir una "convención de nombramiento de fórmulas", sin embargo escribir una convención es difícil ya que hay que tomar en cuenta varias cosas, cómo el nivel educativo de los usuarios, el contexto de dónde se muestran las fórmulas e incluso la "universalidad" de las palabras.

Si la fórmula se muestra sin más contexto, puede ser correcto nombrarla cómo "fórmula área de un cuadrado" o "cálculo de área de un cuadrado", pero si la fórmula sólo se muestra en una sección dónde todo son fórmulas de geometría, se puede escribir "área de un cuadrado" y puede ser totalmente válido.

Lo que hace aparecer la pregunta "¿debería hacerse la app alrededor de la fórmula o la fórmula alrededor de la app?" la cual, no tiene respuesta fija ni correcta, por lo que también deben tomarse en cuenta otras variables.

### Campos a mostrar

Cómo ya se mencionó, no todas las fórmulas requieren los mismos campos, algunas requieren notas acerca del significado de cada variable o notas más generales de cada fórmula.

Tras un corto análisis es posible responder esta pregunta más facilmente. Todas las fórmulas incluyen un nombre y la fórmula misma, muchas fórmulas tienen variables por lo que es útil conocer el nombre y su significado así cómo las unidades que usan o si son adimensionales, de igual forma algunas fórmulas se conocen por más de un nombre por lo que es útil mencionarlo. Por lo tanto, todas las fórmulas hechas deberían de seguir una forma más o menos predeterminada:

```yaml
nombre: nombreFormula,
formula: representacionLaTeX,
variables:
  variable: representaciónLaTeX,
  significado: significado,
  unidades: unidades,
otros-nombres:
  alternativa1,
  alternativa2,
nota: nota
```

Esta forma asegura que gran parte de las fórmulas puedan ser representadas. En algunos casos, ciertos campos van a sobrar, pero se pueden dejar vacíos y se puede poner un mensaje predefinido para esos casos vacíos. Toda esta lógica lleva al siguiente punto.

## Limitaciones técnicas

La aplicación debería ser capaz de tomar los datos correctos y mostrarlos pero la aplicación debería ser independiente de los datos, de cierta forma. Los datos se pueden almacenar de muchas maneras, pero algunos métodos pueden ser más difíciles o incluso pueden ser excesivos.

Los datos son fijos de cierta manera, es decir, no se agregan cada día nuevas fórmulas y no requieren de gran mantenimiento, una vez escritas ahí estarán, por lo tanto, usar una base de datos cómo las usadas por redes sociales o aplicaciones "grandes" sobran para este propósito, sí, es posible hacerlo pero sólo añaden complejidad. Finalmente se decidió hacerlo en archivos "estáticos", es decir, archivos de texto en un formato específico que ayuden a la computadora a entender cómo leer los datos, esto quita complejidad a la ecuación pero añade trabajo manual.

El usar archivos de texto, tiene el beneficio de ser a prueba de futuro, es decir, si alguien más retoma los datos, estos funcionarán sin importar si cambia la tecnología, todos los programas son capaces de leer texto. No necesitan de un servidor "dinámico", al ser permanentes de cierta forma, sólo necesitan leerse, por lo que no necesitan de un servidor que esté escribiendo a ellos continuamente.

Existen muchos formatos disponibles para distribuir este tipo de datos ordenados, YAML, JSON, CSV, TOML, cada uno tiene sus beneficios y para este caso es mejor el uso de JSON, el formate se muestra a continuación

```json
{
    "categoria-subcategoria": [
        {
            "nombre": "nombre",
            "formula": "LaTeX",
            "variables": [
                {
                    "variable": "representacionLaTeX",
                    "significado": "significado",
                    "unidades": "unidades"
                },
                {
                    "variable": "representacionLaTeX",
                    "significado": "significado",
                    "unidades": "unidades"
                }
            ],
            "otros-nombres": [
                "Alternativa 1",
                "Alternativa 2"
            ],
            "nota": "nota"
        },
        {
            "nombre": "nombre",
            "formula": "LaTeX",
            "variables": [
                {
                    "variable": "representacionLaTeX",
                    "significado": "significado",
                    "unidades": "unidades"
                },
                {
                    "variable": "representacionLaTeX",
                    "significado": "significado",
                    "unidades": "unidades"
                }
            ],
            "otros-nombres": [
                "Alternativa 1",
                "Alternativa 2"
            ],
            "nota": "nota"
        }
    ]
}
```

## Conclusión

Aún hay preguntas por responder y hace falta escribir y planear mucho pero las bases comienzan a asentarse. Queda un tanto lejano el lanzamiento de alguna nueva versión de OpenFormula, pero el escribir estándares y planeación es un paso hacia adelante en ese objetivo.

En los próximos días se estará escribiendo una convención de nombramiento para fórmulas para poder comenzar a construir la primer parte de OpenFormula, la aplicación encargada de manejar las bases de datos de forma más sencilla.
