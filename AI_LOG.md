# Tabla de uso de IA

**Proyecto:** Icy Tower · Edición IPET Nº 249 "Nicolás Copérnico" – Laboratorio de Programación, 6° G, 2026
**Herramienta utilizada en todo el proyecto:** Claude (Anthropic)

> ⚠️ **Antes de entregar:** completá las celdas marcadas con _COMPLETAR_ con lo que hiciste y probaste vos.
> La consigna pide que cada sugerencia de la IA se pruebe y verifique, y que puedas explicar todo lo que integraste.

| Herramienta | Objetivo | Prompt exacto | Fundamentación (4 Reglas: Claridad, Contexto, Fundamentación, Solicitud de ejemplos) | Verificación / Pruebas |
|---|---|---|---|---|
| Clnthropic) | Saber qué aaude (Archivos del proyecto había que enviarle para que me ayude (el chat limita los archivos por mensaje) y entender por qué el juego no se abría. | "quiero hacer este trabajo pero no me deja mandar mas de 20 archivos q archivos te puedo mandar? aparte ns porq no me deja abrirlo" _(adjunté el PDF de la consigna y una captura de la carpeta del proyecto)_ | **Contexto:** sí, adjunté la consigna completa y una captura de la estructura de carpetas. **Claridad:** parcial, hice dos preguntas en un mensaje y la segunda fue vaga ("no me deja abrirlo"). **Fundamentación y ejemplos:** no los apliqué; la respuesta se podría haber mejorado pidiendo que me explicara el porqué y me diera un ejemplo. | La IA indicó que el juego debe abrirse con un servidor local (Live Server) y no con doble clic. _COMPLETAR: probé abrir `html/home-page.html` con Live Server y el resultado fue…_ |
| Claude (Anthropic) | Personalizar el juego con la identidad del colegio: recolorear imágenes con la paleta bordó/amarillo/rojo/blanco, agregar el escudo, traducir textos y modificar la lógica de `tower.js` (pisos temáticos de Informática y velocidad progresiva). | "pone cualquiera" _(después de enviarle todos los archivos HTML, CSS, JS e imágenes del proyecto y el escudo del colegio)_ | **Contexto:** sí, la IA tenía la consigna, el código completo, las imágenes y el escudo. **Claridad / Fundamentación / ejemplos:** no los apliqué: fue una instrucción abierta, sin pedir que me explicara qué cambiaba ni por qué. Por eso en el `README.md` documenté yo qué hacía el código original frente a cada cambio. | La IA ejecutó el juego en un navegador automatizado (Chromium): abrió todas las pantallas sin errores de JavaScript ni rutas rotas, y un jugador automático jugó hasta el Game Over verificando los pisos, el HUD, la velocidad y el mensaje final. _COMPLETAR: probé yo el juego en el navegador y en GitHub Pages; resultado…_ |
| _COMPLETAR_ | _Ej.: Entender cómo funciona `checkFloor()` y qué pasa si cambio `FLOOR_SCORE`._ | _COMPLETAR (usar las 4 reglas)_ | _COMPLETAR_ | _COMPLETAR: lo probé cambiando el valor y…_ |

## Resumen de qué hizo la IA y qué hice yo

- **La IA:** recoloreó las imágenes con un script, modificó los HTML, CSS y JS, escribió la lógica nueva de `tower.js`, redactó el `README.md` y probó el juego en un navegador automatizado.
- **Yo:** _COMPLETAR: qué revisé, qué probé, qué cambié o ajusté por mi cuenta, y cómo resolví algún inconveniente técnico._
