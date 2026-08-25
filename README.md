# Pensum Tracker — Ingeniería Mecánica PUCMM

Aplicación web de una sola página para dar seguimiento al pénsum de la carrera de
**Ingeniería Mecánica** de la Pontificia Universidad Católica Madre y Maestra (PUCMM).

Sin instalación, sin servidor, sin dependencias: es un único archivo HTML.
Se abre con doble clic en cualquier navegador moderno.

![estado](https://img.shields.io/badge/asignaturas-85-3fe0ff) ![creditos](https://img.shields.io/badge/cr%C3%A9ditos-217-3fe0ff) ![periodos](https://img.shields.io/badge/per%C3%ADodos-12-3fe0ff)

## Qué hace

- **Malla curricular completa** — 85 asignaturas repartidas en 4 años × 3 períodos (217 créditos).
- **Cuatro estados por asignatura** — aprobada, cursando, disponible y bloqueada por prerrequisito.
- **Trazado de dependencias** — al pasar el cursor sobre una asignatura, el resto se atenúa y se
  encienden sus prerrequisitos y las asignaturas que habilita.
- **Índice acumulado** — promedio ponderado por créditos, con gauge circular.
- **Planificador del próximo período** — lista únicamente lo que ya puedes tomar y suma créditos.
- **Buscador** y filtro para ocultar laboratorios.
- **Guardado automático** en el navegador, con exportación e importación de respaldo en JSON.

## Ver en línea

La aplicación está publicada con GitHub Pages:

**https://TU-USUARIO.github.io/pensum-tracker-pucmm/**

Funciona igual en el celular. En iOS puedes usar *Compartir → Añadir a pantalla de
inicio* para abrirla como si fuera una app.

> El progreso se guarda en el navegador que uses. La versión en línea y la copia
> local llevan progresos separados: para pasar de una a otra, usa **Exportar
> respaldo** e **Importar**.

### Publicar tu propia copia

1. Haz *fork* del repositorio (o clónalo y súbelo al tuyo).
2. Ve a **Settings → Pages**.
3. En *Source* elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
4. Guarda. En un minuto la URL queda activa.

## Uso

1. Abre `index.html` en el navegador (o entra a la URL de arriba).
2. Haz clic en una asignatura para fijarla en el Inspector.
3. Cambia su estado y asígnale la calificación obtenida.
4. El índice, los créditos y los desbloqueos se recalculan al instante.

El progreso se guarda solo en el navegador donde lo usas. Para moverlo a otra
computadora, usa **Exportar respaldo** y luego **Importar** en la otra.

## Sobre los datos

Las asignaturas, horas teóricas, horas prácticas y créditos están transcritos del
pénsum oficial publicado por la Facultad de Ciencias e Ingeniería. Los totales de
créditos de los doce períodos coinciden con los del documento original:

`20 · 18 · 20 · 19 · 20 · 19 · 18 · 22 · 15 · 18 · 17 · 11 = 217`

> **Los prerrequisitos no aparecen en el pénsum oficial.** Los incluidos en esta
> aplicación son una propuesta lógica basada en las cadenas naturales de la carrera
> (cálculo, física, circuitos, materiales, termodinámica, diseño). **Verifícalos con tu
> facultad.** Puedes corregirlos desde el Inspector con el botón *Editar*, y los cambios
> quedan guardados junto a tu progreso.

## Escala de calificaciones

| Nota | Puntos |
|------|--------|
| A    | 4.0    |
| B+   | 3.5    |
| B    | 3.0    |
| C+   | 2.5    |
| C    | 2.0    |
| D    | 1.0    |
| F    | 0.0    |

Las asignaturas de 0 créditos no intervienen en el cálculo del índice.
Si tu facultad usa otra escala, edita la constante `ESCALA` en el archivo.

## Estructura

Todo vive en `index.html`:

- `PENSUM` — arreglo con los doce períodos y sus asignaturas.
- `ESCALA` — tabla de equivalencia de calificaciones.
- El resto es la lógica de estados, métricas y render.

## Licencia

MIT — ver [LICENSE](LICENSE).

Este proyecto no está afiliado ni respaldado oficialmente por la PUCMM.
