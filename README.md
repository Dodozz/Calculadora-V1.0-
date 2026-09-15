# 🧮 Calculadora V2.0

Aplicación web de calculadora con historial de operaciones y cálculo de porcentaje, desarrollada en **HTML, CSS y JavaScript puro** (sin frameworks ni librerías externas). El proyecto documenta un ciclo completo de **análisis, diseño, desarrollo y pruebas de software**, y se utiliza como caso de estudio (Sistema Bajo Prueba) para la materia de **Modelos de Prueba de Software** — UPIICSA, Instituto Politécnico Nacional.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Estado](https://img.shields.io/badge/estado-en%20pruebas-yellow)

---

## 🆕 Novedades de la versión 2.0 (vs. v1.0)

La v2.0 añade una función nueva, corrige tres comportamientos de la v1.0 y reordena la numeración de los requerimientos funcionales (RF).

### Funcionalidad nueva

- **RF-13 — Cálculo de porcentaje (%)**: nuevo botón `%` en el teclado. Su comportamiento cambia según el contexto de la expresión:
  - **Entrada aislada** (sin operador previo): divide el valor entre 100 de inmediato, sin necesidad de `=` (ej. `800` + `%` → `8`).
  - **Aditivo / sustractivo** (tras `+` o `−`): en una expresión `A + B%`, calcula `B% de A` y sustituye a `B` por ese valor parcial; el resultado final se obtiene al presionar `=` (ej. `200 + 20%` muestra `40` y al presionar `=` da `240`).
  - **Multiplicativo / divisivo** (tras `×` o `÷`): convierte `B` a su equivalente decimal `B/100` (ej. `50 × 20%` = `10`).
  - Si se presiona con la pantalla en `0`, o justo después de un operador sin haber introducido un número nuevo, la acción se ignora.

### Correcciones de comportamiento

- **RF-14 (antes RF-8) — Cambio de signo (+/−)**: en v1.0 el número se envolvía como `(-N`, **sin cerrar el paréntesis**, lo que dejaba la expresión desbalanceada y podía provocar `Error: paréntesis` al presionar `=`. En v2.0 se cierra correctamente como `(-N)`, y ahora también es posible revertir un número ya envuelto en negativo de vuelta a positivo presionando el botón otra vez.
- **RF-4 — Retroceso (⌫) tras un resultado**: en v1.0, después de presionar `=`, el botón ⌫ quedaba bloqueado y no hacía nada. En v2.0 permite editar o borrar el resultado dígito por dígito, igual que cualquier otro valor en pantalla.
- **RF-10 (antes RF-11) — Prevención de entradas inválidas**: se agregó la exigencia de que la expresión contenga al menos un operador binario antes de calcular, evitando "cálculos" triviales como `5` + `=` → `5 = 5`.

### Interfaz

- Se añadió el botón `%` al teclado.
- El botón `=` pasó de ocupar el ancho completo de su fila (`grid-column: span 4`) a ocupar 3 columnas (`span 3`), para dejar espacio al nuevo botón `%`.

### Documentación

- Se agregó **`REQUERIMIENTOS.docx`**, el documento de especificación actualizado con la redacción y los criterios de aceptación (CA) de **RF-1 a RF-14** y **RNF-1 a RNF-6**.
- El documento **`Análisis y Diseño (1).docx`** de la v1.0 se conserva en el repositorio como referencia histórica.

### Renumeración de requerimientos funcionales

Al insertar el nuevo RF-13 (porcentaje) y mover el cambio de signo al final como RF-14, los requerimientos que antes eran RF-9 a RF-13 se recorrieron una posición hacia abajo:

| ID en v1.0 | ID en v2.0 | Requerimiento |
|---|---|---|
| RF-1 | RF-1 | Operaciones aritméticas básicas |
| RF-2 | RF-2 | Historial de operaciones |
| RF-3 | RF-3 | Un solo punto decimal por operando |
| RF-4 | RF-4 | Retroceso (⌫) y AC |
| RF-5 | RF-5 | Manejo de errores |
| RF-6 | RF-6 | Control de operadores consecutivos |
| RF-7 | RF-7 | Ingreso y visualización de números |
| RF-9 | RF-8 | Limpieza del historial |
| RF-10 | RF-9 | Visualización diferenciada del resultado |
| RF-11 | RF-10 | Prevención de entradas inválidas |
| RF-12 | RF-11 | Continuidad de operaciones |
| RF-13 | RF-12 | Jerarquía de operaciones y paréntesis |
| *(nuevo)* | RF-13 | Cálculo de porcentaje (%) |
| RF-8 | RF-14 | Cambio de signo (+/−) |

> ⚠️ **Importante para el enfoque de pruebas:** cualquier caso de prueba o matriz de trazabilidad diseñada contra la numeración de v1.0 debe revisarse. Por ejemplo, un CP que apuntaba a "RF-13" esperando la jerarquía de operaciones ahora apuntaría, con el ID v2.0, a una funcionalidad distinta (porcentaje).

---

## 👥 Equipo de trabajo

| Rol | Integrante |
|---|---|
| 📊 Analista | Ramírez Claudio Diana |
| 🎨 Diseñador/a | Valladares López Irene |
| 💻 Desarrollador / Programador | Donovan Adriel Rojo Bojorges |
| 🧪 Tester | Ana Daniela Pérez Hernández |

## 🎯 Contexto y propósito académico

Este repositorio no solo entrega la calculadora funcional, sino que sirve como **práctica integradora para la materia de Modelos de Prueba de Software**. Cada requerimiento funcional fue definido junto con sus criterios de aceptación (CA), los cuales constituyen la base para el diseño de casos de prueba mediante técnicas de caja negra: partición de equivalencia, análisis de valores límite, tablas de decisión y adivinación de errores (*error guessing*).

## ⚙️ Requerimientos funcionales (v2.0)

| ID | ID en v1.0 | Requerimiento |
|---|---|---|
| RF-1 | RF-1 | Operaciones aritméticas básicas (+, −, ×, ÷) con hasta 2 decimales y redondeo |
| RF-2 | RF-2 | Historial de operaciones de la sesión, consultable sin afectar la operación en curso |
| RF-3 | RF-3 | Un solo punto decimal permitido por operando |
| RF-4 | RF-4 | Corrección con Retroceso (⌫) y limpieza total con AC |
| RF-5 | RF-5 | Manejo de errores (p. ej. división entre cero) sin cerrar la aplicación |
| RF-6 | RF-6 | Control de operadores consecutivos (el nuevo reemplaza al anterior) |
| RF-7 | RF-7 | Ingreso y visualización de números dígito por dígito |
| RF-8 | RF-9 | Limpieza total del historial |
| RF-9 | RF-10 | Visualización diferenciada del resultado respecto a la expresión en curso |
| RF-10 | RF-11 | Prevención de entradas que no formen una operación válida |
| RF-11 | RF-12 | Continuidad de operaciones reutilizando el resultado previo |
| RF-12 | RF-13 | Jerarquía de operaciones y soporte de paréntesis |
| RF-13 | — *(nuevo)* | Cálculo de porcentaje (%): entrada aislada, aditivo/sustractivo y multiplicativo/divisivo |
| RF-14 | RF-8 | Cambio de signo (+/−) del número actual |

> 📄 El detalle completo de cada RF con sus criterios de aceptación (CA) se encuentra en **`REQUERIMIENTOS.docx`** (v2.0). El documento **`Análisis y Diseño (1).docx`** conserva la redacción original de la v1.0.

## 🚦 Requerimientos no funcionales

Sin cambios respecto a la v1.0:

| ID | Requerimiento |
|---|---|
| RNF-1 | Usabilidad: interfaz sencilla e intuitiva |
| RNF-2 | Diseño visual ordenado, con botones redondeados |
| RNF-3 | Tiempo de respuesta inmediato, sin retrasos perceptibles |
| RNF-4 | Legibilidad: textos y resultados con tamaño de letra adecuado |
| RNF-5 | Estabilidad ante errores o entradas inválidas |
| RNF-6 | Precisión matemática en el manejo de decimales |

## 🎨 Diseño de interfaz

El diseño sigue un mockup tipo *smartphone*:

- Encabezado con el título "calculadora" y acceso al historial (ícono de reloj 🕒).
- Panel de historial plegable, con opción de "Limpiar".
- Pantalla con la expresión en curso (arriba, en gris) y el resultado grande (abajo, en negro).
- Teclado en cuadrícula de 4 columnas: teclas numéricas en blanco, operadores en azul claro. **Nuevo en v2.0:** la última fila combina la tecla `%` (1 columna) con la tecla `=` en negro, que ahora ocupa 3 columnas (antes ocupaba las 4 como fila completa).

## 🛠️ Tecnologías utilizadas

- **HTML5** — estructura de la interfaz
- **CSS3** (Flexbox y Grid) — estilos, sin frameworks de UI
- **JavaScript (Vanilla)** — lógica de la calculadora, sin librerías externas
- Sin dependencias ni build tools: todo vive en un único archivo `index.html`

## 📁 Estructura del repositorio

```
├── index.html                        # Aplicación completa (HTML + CSS + JS) — v2.0
├── REQUERIMIENTOS.docx                # RF-1 a RF-14 y RNF-1 a RNF-6 actualizados (v2.0)
├── Análisis y Diseño (1).docx         # Documento original de análisis y diseño (v1.0)
└── README.md                          # Este archivo
```

> **Nota de mantenimiento:** el repositorio contiene actualmente dos entradas con el nombre visual "Análisis y Diseño (1).docx" (mismo contenido, mismo tamaño). Es un artefacto típico de subir el mismo archivo dos veces desde macOS con distinta normalización Unicode en los acentos del nombre, no un documento diferente. Puede limpiarse eliminando una de las dos copias con `git rm`.

## 🚀 Instalación y ejecución

No requiere instalación de dependencias.

1. Clona el repositorio:
   ```bash
   git clone https://github.com/<tu-usuario>/<tu-repositorio>.git
   ```
2. Entra a la carpeta del proyecto:
   ```bash
   cd <tu-repositorio>
   ```
3. Abre `index.html` directamente en tu navegador, o sírvelo con una extensión tipo *Live Server*.

## 💡 Ejemplos de uso

| Entrada | Resultado |
|---|---|
| `5 + 3` | `8` |
| `(2 + 3) * 4` | `20` |
| `10 / 0` | `Error: división por cero` |
| `7` seguido de `+/-` | `(−7)` (el signo se envuelve en paréntesis para mantener la expresión válida) |
| `2.5 + 2.5` | `5` (sin ceros decimales innecesarios) |
| `800` seguido de `%` | `8` — *nuevo en v2.0, porcentaje aislado* |
| `200 + 20%` seguido de `=` | `240` — *nuevo en v2.0, porcentaje aditivo* |
| `50 * 20%` seguido de `=` | `10` — *nuevo en v2.0, porcentaje multiplicativo* |
| `5` seguido de `=` | No calcula — *corregido en v2.0, exige un operador binario* |

## 🧪 Enfoque de pruebas

Como parte de la materia de **Modelos de Prueba de Software**, este proyecto se utiliza para aplicar técnicas de diseño de casos de prueba de caja negra sobre los RF y sus criterios de aceptación. Los IDs de RF usados abajo ya corresponden a la numeración de v2.0. Algunos ejemplos de casos derivados:

| Caso | RF relacionado | Técnica | Entrada | Resultado esperado |
|---|---|---|---|---|
| CP-01 | RF-1 | Partición de equivalencia (válida) | `4.256 + 1` | `5.26` (redondeo a 2 decimales) |
| CP-02 | RF-5 | Manejo de errores | `8 / 0` | Mensaje "Error: división por cero"; la app sigue operable |
| CP-03 | RF-6 | Adivinación de errores | `5 + + 3` | Se conserva un solo `+` |
| CP-04 | RF-3 | Valores límite | Segundo punto decimal en un mismo operando | El segundo punto se ignora |
| CP-05 | RF-12 *(antes RF-13)* | Caja negra / jerarquía de operaciones | `2 + 3 * 4` | `14` |
| CP-06 | RF-10 *(antes RF-11)* | Entrada inválida | Presionar `=` con la expresión `5 +` | No ejecuta el cálculo |
| CP-07 | RF-13 *(nuevo)* | Partición de equivalencia (aislado) | `800` + `%` | `8` |
| CP-08 | RF-13 *(nuevo)* | Partición de equivalencia (aditivo) | `200 + 20%` + `=` | `240` |
| CP-09 | RF-14 *(antes RF-8)* | Valores límite | `0` + `+/-` | Permanece en `0` |
| CP-10 | RF-4 | Regresión | Resultado en pantalla + `⌫` | Permite editar el resultado (antes bloqueado en v1.0) |

> Estos casos son un punto de partida; el diseño formal de pruebas (matriz de trazabilidad, técnicas adicionales, evidencias de ejecución) se documenta como entregable independiente de la materia.

## 📌 Estado del proyecto

🟡 **Versión 2.0** — funcionalidad completa según RF-1 a RF-14; incorpora el cálculo de porcentaje y corrige el cambio de signo, el retroceso tras un resultado y la validación de entradas heredados de la v1.0. Actualmente en fase de pruebas.

## 📄 Licencia

Proyecto de uso académico. Puedes agregar la licencia que prefieras (por ejemplo, MIT) según los lineamientos de tu institución.
