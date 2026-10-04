<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Yoselin · Mis 15</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: Georgia, "Times New Roman", serif;
    color: #fff;
    background:
        radial-gradient(circle at 50% 20%, rgba(255,255,255,.12), transparent 25%),
        radial-gradient(circle at 20% 80%, rgba(255,0,70,.25), transparent 30%),
        linear-gradient(135deg, #180006, #5b0018, #160006);
    min-height: 100vh;
    overflow-x: hidden;
}

/* =========================
   FONDO DISCO
========================= */

body::before {
    content: "";
    position: fixed;
    inset: 0;
    pointer-events: none;
    background:
        repeating-linear-gradient(
            120deg,
            transparent 0,
            transparent 45px,
            rgba(255,255,255,.025) 46px,
            transparent 48px
        );
    animation: fondoMovimiento 10s linear infinite;
    z-index: 0;
}

@keyframes fondoMovimiento {
    from {
        transform: translateX(-100px);
    }
    to {
        transform: translateX(100px);
    }
}

/* Luces */

.luz {
    position: fixed;
    width: 45vw;
    height: 120vh;
    top: -20vh;
    left: 50%;
    transform-origin: bottom center;
    background: linear-gradient(
        to top,
        rgba(255,255,255,.20),
        rgba(255,255,255,.04),
        transparent
    );
    filter: blur(8px);
    opacity: .35;
    pointer-events: none;
    z-index: 1;
}

.luz1 {
    animation: girar1 7s linear infinite;
}

.luz2 {
    animation: girar2 9s linear infinite;
}

@keyframes girar1 {
    0% { transform: rotate(-55deg); }
    50% { transform: rotate(55deg); }
    100% { transform: rotate(-55deg); }
}

@keyframes girar2 {
    0% { transform: rotate(55deg); }
    50% { transform: rotate(-55deg); }
    100% { transform: rotate(55deg); }
}

/* =========================
   PARTÍCULAS
========================= */

.particula {
    position: fixed;
    width: 4px;
    height: 4px;
    border-radius: 50%;
    background: white;
    box-shadow: 0 0 10px white, 0 0 20px #fff;
    opacity: .8;
    pointer-events: none;
    animation: flotar linear infinite;
    z-index: 2;
}

@keyframes flotar {
    from {
        transform: translateY(110vh) scale(.5);
        opacity: 0;
    }

    20% {
        opacity: .9;
    }

    80% {
        opacity: .8;
    }

    to {
        transform: translateY(-10vh) scale(1);
        opacity: 0;
    }
}

/* =========================
   CONTENEDOR
========================= */

.contenedor {
    position: relative;
    z-index: 5;
    width: min(920px, 92%);
    margin: auto;
    padding: 35px 0 50px;
}

/* =========================
   BOLA DE ESPEJOS
========================= */

.disco {
    width: 130px;
    height: 130px;
    margin: 10px auto 30px;
    border-radius: 50%;
    background:
        repeating-linear-gradient(
            45deg,
            #fff 0 5px,
            #aaa 6px 10px,
            #444 11px 15px
        );
    box-shadow:
        0 0 20px #fff,
        0 0 45px rgba(255,255,255,.7),
        0 0 90px rgba(255,0,70,.5);
    animation: discoGiro 8s linear infinite;
}

@keyframes discoGiro {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}

/* =========================
   PORTADA
========================= */

.portada {
    text-align: center;
    padding: 55px 20px;
    border: 1px solid rgba(255,255,255,.25);
    border-radius: 30px;
    background: rgba(255,255,255,.08);
    backdrop-filter: blur(14px);
    -webkit-backdrop-filter: blur(14px);
    box-shadow:
        0 20px 60px rgba(0,0,0,.45),
        inset 0 0 30px rgba(255,255,255,.04);
}

.pre-titulo {
    font-size: 15px;
    letter-spacing: 5px;
    text-transform: uppercase;
    color: #eee;
    margin-bottom: 18px;
}

.nombre {
    font-size: clamp(58px, 12vw, 110px);
    line-height: .95;
    font-weight: normal;
    font-style: italic;
    background: linear-gradient(
        90deg,
        #fff,
        #bbb,
        #fff,
        #aaa,
        #fff
    );
    background-size: 300% auto;
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    animation: brilloTexto 4s linear infinite;
    text-shadow: 0 0 25px rgba(255,255,255,.25);
}

@keyframes brilloTexto {
    from { background-position: 0% center; }
    to { background-position: 300% center; }
}

.mis15 {
    margin-top: 20px;
    font-size: clamp(30px, 7vw, 60px);
    letter-spacing: 10px;
    color: #fff;
    text-shadow:
        0 0 10px #fff,
        0 0 30px rgba(255,0,60,.7);
}

/* =========================
   TARJETAS
========================= */

.tarjeta {
    margin-top: 25px;
    padding: 32px 25px;
    text-align: center;
    border-radius: 25px;
    border: 1px solid rgba(255,255,255,.20);
    background: rgba(255,255,255,.08);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    box-shadow:
        0 15px 45px rgba(0,0,0,.35),
        inset 0 0 25px rgba(255,255,255,.03);
}

.titulo-seccion {
    font-size: 18px;
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 18px;
    color: #eee;
}

.fecha {
    font-size: clamp(30px, 7vw, 50px);
    letter-spacing: 5px;
    font-weight: bold;
}

.hora {
    margin-top: 10px;
    font-size: 24px;
    color: #ddd;
}

/* =========================
   UBICACIÓN
========================= */

.lugar {
    font-size: 25px;
    font-weight: bold;
    margin-bottom: 10px;
}

.direccion {
    line-height: 1.7;
    color: #ddd;
    font-size: 18px;
}

.boton {
    display: inline-block;
    margin-top: 22px;
    padding: 14px 25px;
    border-radius: 50px;
    text-decoration: none;
    color: white;
    font-family: Arial, sans-serif;
    font-weight: bold;
    letter-spacing: 1px;
    border: 1px solid rgba(255,255,255,.45);
    background: linear-gradient(
        135deg,
        rgba(255,255,255,.18),
        rgba(255,0,60,.35)
    );
    box-shadow:
        0 0 20px rgba(255,0,60,.25),
        inset 0 0 10px rgba(255,255,255,.08);
    transition: .3s;
}

.boton:hover {
    transform: translateY(-3px) scale(1.03);
    box-shadow:
        0 0 25px rgba(255,255,255,.4),
        0 0 45px rgba(255,0,70,.45);
}

/* =========================
   CUENTA REGRESIVA
========================= */

.contador {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-top: 20px;
}

.tiempo {
    padding: 18px 8px;
    border-radius: 18px;
    background: rgba(0,0,0,.25);
    border: 1px solid rgba(255,255,255,.18);
}

.numero {
    display: block;
    font-size: clamp(28px, 6vw, 45px);
    font-weight: bold;
}

.etiqueta {
    display: block;
    margin-top: 5px;
    font-size: 11px;
    letter-spacing: 2px;
    color: #ccc;
}

/* =========================
   MENSAJE
========================= */

.mensaje {
    font-size: 21px;
    line-height: 1.8;
    color: #eee;
}

.firma {
    margin-top: 25px;
    font-size: 25px;
    font-style: italic;
}

/* =========================
   WHATSAPP
========================= */

.whatsapp {
    background: linear-gradient(
        135deg,
        rgba(255,255,255,.15),
        rgba(130,0,35,.5)
    );
}

/* =========================
   FUEGOS ARTIFICIALES
========================= */

#fuegos {
    position: fixed;
    inset: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 100;
}

/* =========================
   FOOTER
========================= */

footer {
    text-align: center;
    padding: 35px 10px 10px;
    color: #ddd;
    font-size: 15px;
    letter-spacing: 2px;
}

/* =========================
   RESPONSIVE
========================= */

@media (max-width: 600px) {

    .contenedor {
        width: 94%;
        padding-top: 20px;
    }

    .portada {
        padding: 40px 15px;
    }

    .disco {
        width: 100px;
        height: 100px;
    }

    .mis15 {
        letter-spacing: 5px;
    }

    .contador {
        gap: 7px;
    }

    .tiempo {
        padding: 14px 4px;
    }

    .mensaje {
        font-size: 18px;
    }

    .direccion {
        font-size: 16px;
    }
}
</style>
</head>

<body>

<!-- LUCES -->
<div class="luz luz1"></div>
<div class="luz luz2"></div>

<!-- FUEGOS ARTIFICIALES -->
<canvas id="fuegos"></canvas>

<!-- PARTÍCULAS -->
<div class="particula" style="left:8%;animation-duration:8s;"></div>
<div class="particula" style="left:18%;animation-duration:11s;animation-delay:2s;"></div>
<div class="particula" style="left:30%;animation-duration:9s;animation-delay:1s;"></div>
<div class="particula" style="left:43%;animation-duration:12s;animation-delay:3s;"></div>
<div class="particula" style="left:56%;animation-duration:10s;"></div>
<div class="particula" style="left:68%;animation-duration:8s;animation-delay:2s;"></div>
<div class="particula" style="left:80%;animation-duration:11s;"></div>
<div class="particula" style="left:92%;animation-duration:9s;animation-delay:1s;"></div>

<div class="contenedor">

    <!-- PORTADA -->
    <section class="portada">

        <div class="disco"></div>

        <div class="pre-titulo">
            Una noche para recordar
        </div>

        <h1 class="nombre">
            Yoselin
        </h1>

        <div class="mis15">
            MIS 15
        </div>

    </section>

    <!-- FECHA -->
    <section class="tarjeta">

        <div class="titulo-seccion">
            ✨ Una fecha especial ✨
        </div>

        <div class="fecha">
            05 · 12 · 2026
        </div>

        <div class="hora">
            20:00 hs
        </div>

    </section>

    <!-- UBICACIÓN -->
    <section class="tarjeta">

        <div class="titulo-seccion">
            📍 Ubicación
        </div>

        <div class="lugar">
            SALÓN DE JUBILADOS
        </div>

        <div class="direccion">
            Sobre Facundo Quiroga<br>
            frente a Ferretería Avenida
        </div>

        <a
            class="boton"
            href="https://maps.app.goo.gl/r3GvA9zV5Ms2vXLY9?g_st=aw"
            target="_blank"
            rel="noopener noreferrer"
        >
            📍 VER UBICACIÓN
        </a>

    </section>

    <!-- CUENTA REGRESIVA -->
    <section class="tarjeta">

        <div class="titulo-seccion">
            ⏳ Falta cada vez menos
        </div>

        <div class="contador">

            <div class="tiempo">
                <span class="numero" id="dias">00</span>
                <span class="etiqueta">DÍAS</span>
            </div>

            <div class="tiempo">
                <span class="numero" id="horas">00</span>
                <span class="etiqueta">HORAS</span>
            </div>

            <div class="tiempo">
                <span class="numero" id="minutos">00</span>
                <span class="etiqueta">MINUTOS</span>
            </div>

            <div class="tiempo">
                <span class="numero" id="segundos">00</span>
                <span class="etiqueta">SEGUNDOS</span>
            </div>

        </div>

    </section>

    <!-- MENSAJE -->
    <section class="tarjeta">

        <div class="titulo-seccion">
            💖 Con mucho cariño
        </div>

        <div class="mensaje">

            Hay momentos que quedan para siempre
            en el corazón.

            <br><br>

            Y quiero compartir uno de los más
            especiales de mi vida con vos.

            <br><br>

            Te espero para celebrar mis 15.

            <div class="firma">
                Yoselin ✨
            </div>

        </div>

    </section>

    <!-- WHATSAPP -->
    <section class="tarjeta">

        <div class="titulo-seccion">
            💌 Confirmación
        </div>

        <div class="direccion">
            Espero contar con vos en esta noche
            tan especial.
        </div>

        <a
            class="boton whatsapp"
            href="https://wa.me/543743557901?text=Hola%20Yoselin%2C%20quiero%20confirmar%20mi%20asistencia%20a%20tus%2015."
            target="_blank"
            rel="noopener noreferrer"
        >
            💬 CONFIRMAR ASISTENCIA
        </a>

    </section>

    <footer>
        🪩 ✨ Yoselin · Mis 15 · 2026 ✨ 🪩
    </footer>

</div>

<script>

/* =====================================================
   CUENTA REGRESIVA
===================================================== */

const fechaEvento = new Date("2026-12-05T20:00:00-03:00").getTime();

function actualizarCuenta() {

    const ahora = new Date().getTime();
    const diferencia = fechaEvento - ahora;

    if (diferencia <= 0) {

        document.getElementById("dias").textContent = "00";
        document.getElementById("horas").textContent = "00";
        document.getElementById("minutos").textContent = "00";
        document.getElementById("segundos").textContent = "00";

        return;
    }

    const dias = Math.floor(diferencia / (1000 * 60 * 60 * 24));
    const horas = Math.floor(
        (diferencia / (1000 * 60 * 60)) % 24
    );
    const minutos = Math.floor(
        (diferencia / (1000 * 60)) % 60
    );
    const segundos = Math.floor(
        (diferencia / 1000) % 60
    );

    document.getElementById("dias").textContent =
        String(dias).padStart(2, "0");

    document.getElementById("horas").textContent =
        String(horas).padStart(2, "0");

    document.getElementById("minutos").textContent =
        String(minutos).padStart(2, "0");

    document.getElementById("segundos").textContent =
        String(segundos).padStart(2, "0");
}

actualizarCuenta();

setInterval(actualizarCuenta, 1000);


/* =====================================================
   FUEGOS ARTIFICIALES
   Se ejecutan automáticamente al abrir la invitación
===================================================== */

const canvas = document.getElementById("fuegos");
const ctx = canvas.getContext("2d");

let ancho;
let alto;

function ajustarCanvas() {
    ancho = canvas.width = window.innerWidth;
    alto = canvas.height = window.innerHeight;
}

ajustarCanvas();

window.addEventListener("resize", ajustarCanvas);

const colores = [
    "#ffffff",
    "#eeeeee",
    "#c0c0c0",
    "#ff1744",
    "#ff4f81",
    "#ffb6c1"
];

let particulasFuego = [];
let cohetes = [];

function crearCohete() {

    const x = Math.random() * ancho;

    const objetivoY =
        alto * (0.15 + Math.random() * 0.42);

    cohetes.push({
        x: x,
        y: alto + 10,
        objetivoY: objetivoY,
        velocidad: 8 + Math.random() * 3,
        color: colores[
            Math.floor(Math.random() * colores.length)
        ]
    });
}

function explotar(x, y, color) {

    const cantidad = 85 + Math.floor(Math.random() * 45);

    for (let i = 0; i < cantidad; i++) {

        const angulo =
            Math.random() * Math.PI * 2;

        const velocidad =
            1.5 + Math.random() * 5.5;

        particulasFuego.push({
            x: x,
            y: y,

            vx: Math.cos(angulo) * velocidad,
            vy: Math.sin(angulo) * velocidad,

            vida: 1,

            decaimiento:
                0.008 + Math.random() * 0.012,

            tamaño:
                1.2 + Math.random() * 2,

            color: color
        });
    }
}

function dibujarFuegos() {

    ctx.fillStyle = "rgba(10, 0, 8, 0.18)";
    ctx.fillRect(0, 0, ancho, alto);

    /* Cohetes */

    for (let i = cohetes.length - 1; i >= 0; i--) {

        const cohete = cohetes[i];

        cohete.y -= cohete.velocidad;

        ctx.beginPath();

        ctx.arc(
            cohete.x,
            cohete.y,
            2,
            0,
            Math.PI * 2
        );

        ctx.fillStyle = cohete.color;
        ctx.shadowBlur = 15;
        ctx.shadowColor = cohete.color;
        ctx.fill();

        if (cohete.y <= cohete.objetivoY) {

            explotar(
                cohete.x,
                cohete.y,
                cohete.color
            );

            cohetes.splice(i, 1);
        }
    }

    /* Partículas */

    for (
        let i = particulasFuego.length - 1;
        i >= 0;
        i--
    ) {

        const p = particulasFuego[i];

        p.x += p.vx;
        p.y += p.vy;

        p.vy += 0.035;

        p.vx *= 0.985;
        p.vy *= 0.985;

        p.vida -= p.decaimiento;

        if (p.vida <= 0) {
            particulasFuego.splice(i, 1);
            continue;
        }

        ctx.beginPath();

        ctx.arc(
            p.x,
            p.y,
            p.tamaño,
            0,
            Math.PI * 2
        );

        ctx.globalAlpha = p.vida;
        ctx.fillStyle = p.color;

        ctx.shadowBlur = 12;
        ctx.shadowColor = p.color;

        ctx.fill();

        ctx.globalAlpha = 1;
    }

    ctx.shadowBlur = 0;

    requestAnimationFrame(dibujarFuegos);
}


/* =====================================================
   LANZAMIENTO INICIAL
===================================================== */

function lanzarFuegosIniciales() {

    let cantidad = 0;

    const intervalo = setInterval(() => {

        crearCohete();

        cantidad++;

        if (cantidad >= 10) {
            clearInterval(intervalo);
        }

    }, 450);
}


/* =====================================================
   INICIO
===================================================== */

dibujarFuegos();

setTimeout(() => {
    lanzarFuegosIniciales();
}, 500);


/* Fuegos adicionales durante unos segundos */

setTimeout(() => {
    crearCohete();
}, 3500);

setTimeout(() => {
    crearCohete();
}, 4300);

setTimeout(() => {
    crearCohete();
}, 5100);

</script>

</body>
</html>
