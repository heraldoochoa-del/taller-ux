# Auditoría y Rediseño de UX/UI - App de Inscripción / Notas

## 1. Auditoría de Heurísticas de Nielsen y Leyes de UX

| Heurística / Ley | Problema Encontrado | Solución Aplicada |
| :--- | :--- | :--- |
| **Visibilidad del estado** | Al enviar el formulario no había feedback visual del progreso ni mensaje de confirmación. | Se agregó mensaje de estado dinámico (`Enviando...`, éxito/error) con `role="status"`. |
| **Coincidencia con el mundo real** | Botones con etiquetas genéricas como "ok" y comandos de sistema poco claros. | Uso de microcopia clara ("Inscribirme", "Limpiar formulario") centrada en la persona. |
| **Control y libertad** | Acción destructiva de borrar campos se ejecutaba sin pedir confirmación. | Confirmación previa antes de limpiar (`confirm()`) y opción de cancelar la acción. |
| **Prevención de errores** | Se permitían envíos con campos vacíos o correos con formato inválido. | Validación interactiva (`required`, `type="email"`) bloqueando envíos con datos incompletos. |
| **Reconocer, no recordar** | Los datos en las entradas desaparecían y faltaban etiquetas visibles. | Uso de etiquetas `<label>` vinculadas (`for`/`id`) y marcadores de posición de ejemplo. |
| **Ley de Fitts** | Botones pequeños y pegados, aumentando el riesgo de clics erróneos. | Botón principal de tamaño amplio (`min-height: 44px`) y separado por `24px` del secundario. |
| **Ley de Hick** | Opciones de selección presentadas en una sola lista desordenada. | Agrupación de opciones mediante `<optgroup>` divididas por categorías claras. |
| **Ley de Miller** | Formulario extenso presentado en un solo bloque continuo. | División del formulario en dos secciones lógicas numeradas usando `<fieldset>` y `<legend>`. |

---

## 2. Accesibilidad y Estándares Visuales

- **Etiquetas y atributos**: Uso de `<label>` en todos los campos e inclusión de texto alternativo (`alt`) descriptivo en la imagen principal.
- **Contraste de color**: Variables CSS definidas en `:root` garantizando una relación de contraste superior a 4.5:1 (WCAG AA).
- **Foco visible**: Implementación de `:focus-visible` con borde de alto contraste (`#f59e0b`) para navegación completa por teclado (`Tab` / `Enter`).
- **Áreas táctiles**: Altura mínima de `44px` en entradas y botones.

---

## 3. Resultados de Auditoría con Lighthouse

- **Puntaje de Accesibilidad inicial (versión original)**: ~65 / 100
- **Puntaje de Accesibilidad final (versión rediseñada)**: **100 / 100**
