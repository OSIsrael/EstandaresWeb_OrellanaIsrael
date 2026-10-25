# Parte 3 – Respuesta y Corrección a la Auditoría

* **Estudiante Evaluado (Propietario):** Israel Sebastián Orellana Solano (N.º de lista 20)
* **Estudiante Auditor:** Denisse Estefanía Paredes Patiño (N.º de lista 21)
* **Fecha de corrección:** Octubre de 2026

---

## Tabla de Respuestas a los Hallazgos

| N.º de hallazgo | Decisión (acepta o refuta) | Justificación con la norma | Evidencia antes y después | Commit |
| :---: | :--- | :--- | :--- | :--- |
| **1** | Acepta y corrige | Se eliminó el ancho mínimo rígido (`min-width: 400px`) en la tabla y se aseguró que el contenedor sea totalmente fluido, cumpliendo de manera estricta con **WCAG 2.2 Criterio 1.4.10 (Reflow)** sin requerir trucos con `overflow-x`. | *Antes:* Tabla con ancho fijo que provocaba desborde a 360px.<br>*Después:* Contenedor adaptado de forma fluida a pantallas móviles pequeñas. | `Ajustar tabla para evitar desborde a 360px` |
| **2** | Acepta y corrige | Se reubicó el bloque `<aside>` al final del código fuente (`index.html`) dentro del `<main>`, garantizando una secuencia de lectura lineal lógica para lectores de pantalla, conforme a **WCAG 2.2 Criterio 1.3.2 (Meaningful Sequence)**, manteniéndolo en su posición visual mediante Grid Areas. | *Antes:* `<aside>` ubicado al inicio del DOM alterando el orden de lectura.<br>*Después:* `<aside>` al final del DOM, preservando el orden semántico correcto. | `Reordenar aside al final del DOM` |
| **3** | Acepta y corrige | Se añadió un elemento textual de ayuda visible (`<small>`) enlazado mediante el atributo `aria-describedby` al campo de teléfono, cumpliendo con **WCAG 2.2 Criterio 3.3.2 (Labels or Instructions)**. | *Antes:* Campo de teléfono sin instrucción visible previa.<br>*Después:* Texto de ayuda claro y accesible debajo del input. | `Anadir texto de ayuda en teléfono` |
| **4** | Acepta y corrige | Se agregaron los atributos `autocomplete` correspondientes (`name`, `email`, `tel`) en los campos del formulario, cumpliendo con **WCAG 2.2 Criterio 1.3.5 (Identify Input Purpose)**. | *Antes:* Campos de datos personales sin propósito autocompletable.<br>*Después:* Inputs con sus respectivos tokens de `autocomplete`. | `Anadir autocomplete` |
| **5** | Acepta y corrige | Se oscureció el tono del color de los bordes (`--color-borde` cambiado a `#595959`) para superar el umbral de contraste estipulado de 3:1 para componentes de interfaz, conforme a **WCAG 2.2 Criterio 1.4.11 (Non-text Contrast)**. | *Antes:* Bordes con contraste de ~1.5:1.<br>*Después:* Bordes con contraste superior a 3:1 sobre fondo blanco. | `Mejorar contrastes de bordes de interfaz` |
| **6** | Acepta y corrige | Se ajustó el color de fondo del botón en estado `hover` (`--color-secundario` cambiado a `#004085`) para garantizar que el texto blanco cumpla con la relación mínima de contraste de 4.5:1 exigida por **WCAG 2.2 Criterio 1.4.3 (Contrast Minimum)**. | *Antes:* Contraste en hover de 3.39:1 (Fallo).<br>*Después:* Contraste superior a 4.5:1 (Pasa la norma). | `Corregir contraste del botón en hover` |
| **7** | Acepta y corrige | Se incorporó una nota aclaratoria visible en el inicio del formulario indicando de forma explícita que todos los campos son requeridos, cumpliendo con **WCAG 2.2 Criterio 3.3.2 (Labels or Instructions)**. | *Antes:* Formulario sin advertencia general de obligatoriedad.<br>*Después:* Aviso textual visible antes de los campos. | `Anadir aviso de campos obligatorios` |
| **8** | Acepta y corrige | Se integró la restricción `min` en la fecha y valores de `min`/`max` restrictivos (08:00 a 18:00) en el campo de hora del formulario, alineándolos coherentemente con los horarios operativas descritos en la tabla de servicios. | *Antes:* Fechas pasadas y horas fuera de rango permitidas.<br>*Después:* Validación nativa acotada al horario real de la clínica. | `Restricciones de fecha y hora coherentes` |
| **9** | Acepta y corrige | Se implementó un enlace de salto accesible (*Skip Link*) al comienzo absoluto del cuerpo del documento (`<body>`), cumpliendo con **WCAG 2.2 Criterio 2.4.1 (Bypass Blocks)** y permitiendo a los usuarios de teclado evitar los bloques repetitivos de navegación. | *Antes:* Inexistencia de mecanismo rápido para omitir el menú.<br>*Después:* Enlace visualmente oculto que se revela al recibir el foco del teclado. | `Anadir skip-link para saltar al contenido` |

---

## Conclusión
Todas las observaciones realizadas en la auditoría cruzada fueron aceptadas y resueltas mediante commits progresivos, limpios y descriptivos en el repositorio oficial. Las modificaciones aplicadas garantizan el cumplimiento estricto de las directrices WCAG 2.2 a nivel AA y las especificaciones WHATWG/W3C.