# 🧮 Calculadora V1.0

Aplicación web de calculadora con historial de operaciones, desarrollada en **HTML, CSS y JavaScript puro** (sin frameworks ni librerías externas). El proyecto documenta un ciclo completo de **análisis, diseño, desarrollo y pruebas de software**, y se utiliza como caso de estudio (Sistema Bajo Prueba) para la materia de **Modelos de Prueba de Software** — UPIICSA, Instituto Politécnico Nacional.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Estado](https://img.shields.io/badge/estado-en%20pruebas-yellow)

---

## 📖 Descripción general

La calculadora permite realizar operaciones aritméticas básicas (suma, resta, multiplicación y división), respetando la jerarquía de operaciones y el uso de paréntesis. Cuenta con un historial de operaciones consultable durante la sesión, manejo de errores (como la división entre cero) sin interrumpir el uso de la app, y una interfaz pensada para ser clara, legible y de respuesta inmediata.

El desarrollo partió de un documento formal de **Análisis y Diseño**, en el que se definieron los requerimientos funcionales (RF) y no funcionales (RNF) junto con sus criterios de aceptación (CA), y un mockup de interfaz tipo *smartphone* que guió la implementación visual.

## 👥 Equipo de trabajo

| Rol | Integrante |
|---|---|
| 📊 Analista | Ramírez Claudio Diana |
| 🎨 Diseñador/a | Valladares López Irene |
| 💻 Desarrollador / Programador | Donovan Adriel Rojo Bojorges |
| 🧪 Tester | Ana Daniela Pérez Hernández |

## 🎯 Contexto y propósito académico

Este repositorio no solo entrega la calculadora funcional, sino que sirve como **práctica integradora para la materia de Modelos de Prueba de Software**. Cada requerimiento funcional fue definido junto con sus criterios de aceptación (CA), los cuales constituyen la base para el diseño de casos de prueba mediante técnicas de caja negra: partición de equivalencia, análisis de valores límite, tablas de decisión y adivinación de errores (*error guessing*).

## ⚙️ Requerimientos funcionales

| ID | Requerimiento |
|---|---|
| RF-1 | Operaciones aritméticas básicas (+, −, ×, ÷) con hasta 2 decimales y redondeo |
| RF-2 | Historial de operaciones de la sesión, consultable sin afectar la operación en curso |
| RF-3 | Un solo punto decimal permitido por operando |
| RF-4 | Corrección con Retroceso (⌫) y limpieza total con AC |
| RF-5 | Manejo de errores (p. ej. división entre cero) sin cerrar la aplicación |
| RF-6 | Control de operadores consecutivos (el nuevo reemplaza al anterior) |
| RF-7 | Ingreso y visualización de números dígito por dígito |
| RF-8 | Limpieza total del historial |
| RF-9 | Visualización diferenciada del resultado respecto a la expresión en curso |
| RF-10 | Prevención de entradas que no formen una operación válida |
| RF-11 | Continuidad de operaciones reutilizando el resultado previo |
| RF-12 | Jerarquía de operaciones y soporte de paréntesis |
| RF-13 | Cálculo de porcentaje (%), con comportamiento dinámico según el operador previo |
| RF-14 | Cambio de signo (+/−) del número actual |
| RF-15 | Recuperación del valor en memoria (MR) |
| RF-16 | Limpieza de la memoria (MC) |
| RF-17 | Adición del valor en pantalla a la memoria (M+) |
| RF-18 | Sustracción del valor en pantalla a la memoria (M-) |
| RF-19 | Indicador visual ("M") de memoria activa |

> 📄 El detalle completo de cada RF con sus criterios de aceptación (CA) se encuentra en los documentos de requerimientos (**REQUERIMIENTOS.docx**, **REQUERIMIENTOS_3.docx**) y **Análisis y Diseño** incluidos en el repositorio.

## 🚦 Requerimientos no funcionales

| ID | Requerimiento |
|---|---|
| RNF-1 | Usabilidad: interfaz sencilla e intuitiva |
| RNF-2 | Diseño visual oscuro, ordenado y consistente, con botones cuadrados de alto contraste |
| RNF-3 | Tiempo de respuesta inmediato, sin retrasos perceptibles |
| RNF-4 | Legibilidad: textos y resultados con tamaño de letra adecuado |
| RNF-5 | Estabilidad ante errores o entradas inválidas |
| RNF-6 | Precisión matemática en el manejo de decimales |

## 🎨 Diseño de interfaz

El diseño sigue un mockup tipo *smartphone* en **tema oscuro** (RNF-2):

- Encabezado con el título "calculadora", el indicador de memoria activa ("M", RF-19) y acceso al historial (ícono de reloj 🕒).
- Panel de historial plegable, con opción de "Limpiar".
- Pantalla oscura con la expresión en curso (arriba, en gris) y el resultado grande (abajo, en blanco).
- Teclado en cuadrícula 4×4 de botones cuadrados: fila de memoria (MC, MR, M+, M-), AC y paréntesis en tonos distintivos, operadores en azul, y la tecla "=" ocupando el ancho completo.

## 🛠️ Tecnologías utilizadas

- **HTML5** — estructura de la interfaz
- **CSS3** (Flexbox y Grid) — estilos, sin frameworks de UI
- **JavaScript (Vanilla)** — lógica de la calculadora, sin librerías externas
- Sin dependencias ni build tools: todo vive en un único archivo `index.html`

## 📁 Estructura del repositorio

```
├── index.html                     # Aplicación completa (HTML + CSS + JS)
├── REQUERIMIENTOS.docx            # Requerimientos funcionales y no funcionales (versión inicial)
├── REQUERIMIENTOS_3.docx          # Requerimientos actualizados (RF-13 a RF-19, RNF-2 tema oscuro)
├── Análisis y Diseño (1).docx     # Documento de análisis y diseño con mockups de interfaz
└── README.md                      # Este archivo
```

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
| `7` seguido de `+/-` | `-7` |
| `2.5 + 2.5` | `5` (sin ceros decimales innecesarios) |
| `200 + 20%` seguido de `=` | `240` (20% de 200 se suma a 200) |
| `7` seguido de `M+`, luego `AC`, luego `MR` | `7` (recupera el valor guardado en memoria) |

## 🧪 Enfoque de pruebas

Como parte de la materia de **Modelos de Prueba de Software**, este proyecto se utiliza para aplicar técnicas de diseño de casos de prueba de caja negra sobre los RF y sus criterios de aceptación. Algunos ejemplos de casos derivados:

| Caso | RF relacionado | Técnica | Entrada | Resultado esperado |
|---|---|---|---|---|
| CP-01 | RF-1 | Partición de equivalencia (válida) | `4.256 + 1` | `5.26` (redondeo a 2 decimales) |
| CP-02 | RF-5 | Manejo de errores | `8 / 0` | Mensaje "Error: división por cero"; la app sigue operable |
| CP-03 | RF-6 | Adivinación de errores | `5 + + 3` | Se conserva un solo `+` |
| CP-04 | RF-3 | Valores límite | Segundo punto decimal en un mismo operando | El segundo punto se ignora |
| CP-05 | RF-13 | Caja negra / jerarquía de operaciones | `2 + 3 * 4` | `14` |
| CP-06 | RF-11 | Entrada inválida | Presionar `=` con la expresión `5 +` | No ejecuta el cálculo |

> Estos casos son un punto de partida; el diseño formal de pruebas (matriz de trazabilidad, técnicas adicionales, evidencias de ejecución) se documenta como entregable independiente de la materia.

## 📌 Estado del proyecto

🟡 **Versión 3.0 (preliminar)** — funcionalidad completa según RF-1 a RF-19 (incluye porcentaje, cambio de signo y funciones de memoria MC/MR/M+/M-) y diseño en tema oscuro (RNF-2), actualmente en fase de pruebas.

## 📄 Licencia

Proyecto de uso académico. Puedes agregar la licencia que prefieras (por ejemplo, MIT) según los lineamientos de tu institución.
