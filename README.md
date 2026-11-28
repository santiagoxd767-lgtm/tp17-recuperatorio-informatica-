# 🧗 Icy Tower · Edición IPET Nº 249 "Nicolás Copérnico"

| | |
|---|---|
| **Colegio** | IPET Nº 249 "Nicolás Copérnico" – Córdoba |
| **Especialidad** | Informática |
| **Asignatura** | Laboratorio de Programación |
| **Curso** | 6° G |
| **Año** | 2026 |
| **Alumno** | _tito santiago_ |
| **Trabajo** | Trabajo Práctico Recuperatorio: Personalización y Despliegue de *Icy Tower* |

▶️ **Jugar online (GitHub Pages):** _COMPLETAR: https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/_
video de yt https://youtu.be/nQOCc7mJY5M

---

## 📌 Créditos y repositorio base

Este proyecto es una adaptación del juego **Icy Tower** (HTML, CSS y JavaScript) del repositorio
[chavi362/Icy-Tower](https://github.com/chavi362/Icy-Tower), publicado bajo licencia MIT.
Toda la lógica del juego, el sistema de usuarios y la estructura base pertenecen al proyecto original y a sus colaboradores.
El escudo del IPET Nº 249 pertenece al colegio.

## 🎨 Resumen de la adaptación

**Identidad visual del colegio**
- Paleta institucional: **bordó `#7B1E3A`**, **amarillo `#F2C200`**, **rojo `#C8102E`** y **blanco**. Las variables están definidas en `css/school-theme.css`.
- Fondo celeste con nieve → degradé bordó; ladrillos naranjas → ladrillos bordó; títulos azul metálico → amarillo metálico.
- Plataformas en colores del colegio: amarilla (nivel inicial), blanca y roja a medida que se avanza.
- Personajes con ropa en bordó y amarillo.
- **Escudo del IPET Nº 249** y datos del colegio y la especialidad visibles en cada pantalla (portada, menús y pantalla de juego).
- Interfaz traducida al español (menús, formularios, mensajes del juego).

**Temática de Informática (lógica en JavaScript)**
- **Pisos temáticos:** cada 10 plataformas (30 puntos) se sube de piso: *Hardware → Sistemas operativos → Redes → Programación → Bases de datos → Ciberseguridad → Inteligencia artificial → Nivel Copérnico 249*.
- **Dificultad progresiva:** cuanto más alto el piso, más rápido sube la torre.
- **Mensajes propios** al empezar (“¡A LA TORRE!”) y al perder (“Segmentation fault (core dumped)”, “Error 404: plataforma no encontrada”…).

**Correcciones técnicas (portabilidad en GitHub Pages)**
- `icy-tower-home.html` cargaba `../JS_GAME/score.js`, una carpeta que no existe → se eliminó la referencia rota.
- `high scores.png` se renombró a `high_scores.png` (los espacios en nombres de archivo dan problemas en URLs).
- `game-scores.html` no tenía `<meta charset>` y los acentos se veían mal → se agregó.
- Se verificó que **todas las rutas son relativas** y respetan mayúsculas/minúsculas (GitHub Pages distingue entre `Home.html` y `home.html`).

## 🔧 Archivos modificados y qué cambió (Etapa 3)

### `js/tower.js` (lógica del juego)

| Qué hacía el código original | Qué hace ahora |
|---|---|
| `movingScreen()` movía las plataformas hacia abajo con una **velocidad fija**: `blocks[i].y + gameConf.velocity[1]`. | Usa la función nueva `currentSpeed()`: `velocidad_base + piso × 0.04`, con tope del **doble** de la velocidad base. Cuanto más alto llegás, más rápido sube la torre. |
| La única progresión eran los "steps" (a los 25 y 50 puntos cambia la imagen de las plataformas y empiezan a moverse). | Se **mantienen** esos steps y se suman los **pisos**: `checkFloor()` calcula `piso = Math.floor(puntaje / 30)`. Si el piso aumentó, guarda el nuevo piso y arma un cartel. |
| No había ningún aviso al avanzar. | `drawFloorBanner()` dibuja un cartel en el canvas (“PISO 2 · Redes”) durante 2,5 segundos, y `updateFloorHud()` actualiza el recuadro “Piso N” al costado del juego. |
| Al empezar decía “LET'S START” y al perder “your score is …”. Los degradés de los textos eran magenta/verde/rojo/azul. | Dice “¡A LA TORRE!” y “puntaje: …”. Los degradés usan amarillo y blanco. |
| Al perder solo aparecía “GAME OVER”. | `showGameOverMessage()` elige al azar un mensaje de programación y muestra a qué piso llegaste. |

Todos los cambios están marcados en el código con comentarios `[IPET 249]` (indicando cómo era antes).

### Otros archivos

| Archivo | Cambio |
|---|---|
| `css/school-theme.css` (**nuevo**) | Variables de la paleta del colegio, estilo del escudo, HUD del piso, panel de puntaje y mensaje de Game Over. |
| `css/*.css` (8 archivos) | Colores originales (dorado, azul, magenta) reemplazados por las variables de la paleta del colegio. |
| `html/*.html` (8 archivos) | Se carga `school-theme.css`, se agrega el escudo, se traducen los textos y se corrigen rutas. `tower.html` suma el HUD de piso y el mensaje de Game Over. |
| `js/login-sign-in.js`, `js/iframe-hello-user.js`, `js/game-scores.js` | Solo se traducen textos al español (no cambia la lógica). |
| `image/*` | Imágenes recoloreadas con la paleta (fondo, ladrillos, plataformas, títulos, personajes, logo, íconos) y `escudo-ipet249.png` (nuevo). |
| `index.html` (**nuevo**) | Redirige a `html/home-page.html` para que la URL de GitHub Pages abra el juego directamente. |

## 🎮 Instrucciones de uso

1. Abrí el juego (enlace de GitHub Pages arriba).
2. **Registrate** con tu nombre, un correo y una contraseña (mínimo 8 caracteres, con letras y números). Los datos se guardan solo en tu navegador (`localStorage`).
3. Tocá la imagen central → **Nuevo juego** → elegí tu personaje → elegí el nivel.
4. Elegí si querés música de fondo y ¡a escalar!

**Niveles:** *Principiante*, *Avanzado* y *Campeones* cambian la velocidad de la torre y la distancia entre plataformas.

### Controles

| Tecla / gesto | Acción |
|---|---|
| ⬅️ / ➡️ | Moverse a la izquierda / derecha |
| ⬆️ (mantener) | Saltar (cuanto más se mantiene, más alto) |
| Celular: tocar la pantalla / deslizar a los costados | Saltar / moverse |

**Puntaje:** 3 puntos por cada plataforma en la que saltás. Si tocás el piso después de pasar las primeras plataformas, se termina el juego.

## 💻 Ejecutar en local

El juego **no funciona** abriendo el HTML con doble clic (el navegador bloquea recursos). Usá un servidor local:

- VS Code → extensión **Live Server** → clic derecho en `html/home-page.html` → *Open with Live Server*, o
- `python -m http.server` en la carpeta del proyecto y abrir `http://localhost:8000/html/home-page.html`.

## 🤖 Uso de Inteligencia Artificial

La tabla de transparencia está en [`AI_LOG.md`](AI_LOG.md).
