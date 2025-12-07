# FoxiCODE

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8" />
    <title>ArCLam - Comunidad</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="ArCLam - Comunidad en Discord" />

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
        }

        body {
            background: radial-gradient(circle at top, #1a1a1a 0, #050505 50%, #000 100%);
            color: #f5f5f5;
            min-height: 100vh;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        .glow {
            text-shadow: 0 0 8px rgba(0, 255, 180, 0.8), 0 0 16px rgba(0, 180, 255, 0.6);
        }

        header {
            padding: 16px 8%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-bottom: 1px solid rgba(0, 255, 200, 0.15);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 10;
            background: rgba(0, 0, 0, 0.6);
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-symbol {
            width: 36px;
            height: 36px;
            border-radius: 12px;
            border: 2px solid #00ffc8;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #00ffc8;
            font-weight: 800;
            font-size: 20px;
            box-shadow: 0 0 15px rgba(0, 255, 200, 0.6);
        }

        .logo-text-main {
            font-size: 20px;
            font-weight: 700;
        }

        .logo-text-sub {
            font-size: 11px;
            color: #a0a0a0;
        }

        nav {
            display: flex;
            gap: 18px;
            font-size: 14px;
        }

        nav a {
            position: relative;
            padding-bottom: 4px;
        }

        nav a::after {
            content: "";
            position: absolute;
            left: 0;
            bottom: 0;
            height: 2px;
            width: 0;
            background: linear-gradient(90deg, #00ffc8, #00b4ff);
            transition: width 0.25s;
        }

        nav a:hover::after {
            width: 100%;
        }

        .btn-small {
            padding: 6px 16px;
            border-radius: 999px;
            border: 1px solid #00ffc8;
            font-size: 13px;
            cursor: pointer;
            background: transparent;
            color: #00ffc8;
            transition: 0.2s;
        }

        .btn-small:hover {
            background: #00ffc8;
            color: #000;
            box-shadow: 0 0 16px rgba(0, 255, 200, 0.7);
        }

        main {
            padding: 40px 8% 60px;
        }

        .hero {
            display: grid;
            grid-template-columns: minmax(0, 3fr) minmax(0, 2.2fr);
            gap: 40px;
            align-items: center;
        }

        .hero-title {
            font-size: clamp(32px, 5vw, 46px);
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 12px;
        }

        .hero-highlight {
            background: linear-gradient(90deg, #00ffc8, #00b4ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .hero-subtitle {
            font-size: 15px;
            color: #c2c2c2;
            max-width: 520px;
            margin-bottom: 20px;
        }

        .hero-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 24px;
        }

        .tag {
            font-size: 11px;
            padding: 4px 10px;
            border-radius: 999px;
            border: 1px solid rgba(0, 255, 200, 0.35);
            color: #9df8e9;
            background: rgba(0, 0, 0, 0.6);
        }

        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .btn-primary {
            padding: 10px 22px;
            border-radius: 999px;
            border: none;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            background: linear-gradient(120deg, #00ffc8, #00b4ff);
            box-shadow: 0 0 16px rgba(0, 255, 200, 0.7);
            color: #000;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary span {
            font-size: 18px;
        }

        .btn-ghost {
            padding: 10px 16px;
            border-radius: 999px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            background: transparent;
            color: #ddd;
            font-size: 13px;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .btn-ghost span {
            font-size: 17px;
        }

        .hero-meta {
            margin-top: 16px;
            font-size: 11px;
            color: #8a8a8a;
        }

        .hero-card {
            border-radius: 20px;
            border: 1px solid rgba(0, 255, 200, 0.25);
            background: radial-gradient(circle at top left, rgba(0, 255, 200, 0.08), transparent 50%),
                        radial-gradient(circle at bottom right, rgba(0, 180, 255, 0.1), transparent 55%),
                        #050505;
            box-shadow: 0 0 40px rgba(0, 255, 200, 0.15);
            padding: 18px 18px 20px;
            position: relative;
            overflow: hidden;
        }

        .hero-card::before {
            content: "";
            position: absolute;
            width: 260px;
            height: 260px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(0, 255, 200, 0.18), transparent 60%);
            top: -120px;
            right: -80px;
            opacity: 0.8;
            filter: blur(1px);
        }

        .hero-card-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 12px;
        }

        .pill {
            font-size: 10px;
            padding: 4px 10px;
            border-radius: 999px;
            border: 1px solid rgba(0, 255, 200, 0.6);
            color: #9fffea;
            background: rgba(0, 0, 0, 0.75);
        }

        .status-dot {
            width: 9px;
            height: 9px;
            border-radius: 50%;
            background: #00ff88;
            box-shadow: 0 0 8px rgba(0, 255, 136, 0.9);
            display: inline-block;
        }

        .hero-card-title {
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 6px;
        }

        .hero-card-desc {
            font-size: 12px;
            color: #d0d0d0;
            margin-bottom: 12px;
        }

        .stat-grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 10px;
            margin-bottom: 14px;
        }

        .stat-box {
            padding: 8px;
            border-radius: 10px;
            border: 1px solid rgba(0, 255, 200, 0.25);
            background: rgba(0, 0, 0, 0.5);
            font-size: 11px;
        }

        .stat-label {
            color: #9fa3b0;
            margin-bottom: 4px;
        }

        .stat-value {
            font-weight: 700;
            color: #f5f5f5;
        }

        .hero-card-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 11px;
            color: #a7a7a7;
        }

        .badge-soft {
            padding: 3px 8px;
            border-radius: 999px;
            border: 1px solid rgba(0, 255, 200, 0.3);
            background: rgba(0, 0, 0, 0.6);
            color: #9fffea;
            font-size: 10px;
        }

        section {
            margin-top: 50px;
        }

        .section-title {
            font-size: 20px;
            margin-bottom: 6px;
        }

        .section-sub {
            font-size: 13px;
            color: #b0b0b0;
            margin-bottom: 14px;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 16px;
        }

        .feature-card {
            border-radius: 14px;
            border: 1px solid rgba(255, 255, 255, 0.08);
            background: rgba(5, 5, 5, 0.9);
            padding: 12px 14px;
            font-size: 12px;
        }

        .feature-title {
            font-weight: 600;
            margin-bottom: 4px;
            color: #fefefe;
        }

        .feature-tag {
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 0.06em;
            color: #00ffc8;
            margin-bottom: 6px;
        }

        footer {
            margin-top: 50px;
            padding-top: 16px;
            border-top: 1px solid rgba(255, 255, 255, 0.08);
            font-size: 11px;
            color: #808080;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 12px;
        }

        footer a {
            color: #9fffea;
            font-size: 11px;
        }

        /* Responsive */
        @media (max-width: 850px) {
            header {
                padding: 12px 5%;
            }
            main {
                padding: 26px 5% 40px;
            }
            .hero {
                grid-template-columns: minmax(0, 1fr);
            }
        }

        @media (max-width: 600px) {
            nav {
                display: none;
            }
        }
    </style>
</head>
<body>
<header>
    <div class="logo">
        <div class="logo-symbol">A</div>
        <div>
            <div class="logo-text-main glow">ArCLam</div>
            <div class="logo-text-sub">Comunidad en Discord</div>
        </div>
    </div>

    <nav>
        <a href="#inicio">Inicio</a>
        <a href="#features">Qué es</a>
        <a href="#discord">Discord</a>
    </nav>

    <button class="btn-small" onclick="scrollToSection('discord')">
        Unirme al Discord
    </button>
</header>

<main>
    <!-- HERO -->
    <section id="inicio" class="hero">
        <div>
            <h1 class="hero-title">
                Bienvenido a <span class="hero-highlight">ArCLam</span><br />
                tu zona segura en la red.
            </h1>
            <p class="hero-subtitle">
                ArCLam es una comunidad en Discord pensada para compartir, aprender
                y colaborar. Charla, proyectos, ayuda y buen ambiente en un solo sitio.
            </p>

            <div class="hero-tags">
                <span class="tag">💬 Comunidad activa</span>
                <span class="tag">🧠 Aprendizaje colaborativo</span>
                <span class="tag">🛡️ Respeto & seguridad</span>
            </div>

            <div class="hero-actions">
                <a href="https://discord.gg/3FZEukEv" target="_blank" rel="noopener">
                    <button class="btn-primary">
                        <span>⚡</span> Entrar a ArCLam
                    </button>
                </a>
                <button class="btn-ghost" onclick="copyDiscordLink()">
                    <span>📋</span> Copiar invitación
                </button>
            </div>

            <p class="hero-meta">
                Invitación oficial: <code id="discord-link">https://discord.gg/3FZEukEv</code>
            </p>
        </div>

        <!-- Card derecha -->
        <div class="hero-card">
            <div class="hero-card-header">
                <span class="pill">Panel de estado ArCLam</span>
                <span><span class="status-dot"></span> Online</span>
            </div>
            <div class="hero-card-title">Servidor Discord ArCLam</div>
            <div class="hero-card-desc">
                Espacio de comunidad: charlas, soporte, proyectos, ideas y
                colaboración entre miembros.
            </div>

            <div class="stat-grid">
                <div class="stat-box">
                    <div class="stat-label">Miembros</div>
                    <div class="stat-value">+100</div>
                </div>
                <div class="stat-box">
                    <div class="stat-label">Canales</div>
                    <div class="stat-value">Texto & Voz</div>
                </div>
                <div class="stat-box">
                    <div class="stat-label">Estado</div>
                    <div class="stat-value">Activo</div>
                </div>
            </div>

            <div class="hero-card-footer">
                <span>Invitación permanente • Moderación activa</span>
                <span class="badge-soft">ArCLam • Discord</span>
            </div>
        </div>
    </section>

    <!-- FEATURES -->
    <section id="features">
        <h2 class="section-title">¿Qué encontrarás en ArCLam?</h2>
        <p class="section-sub">
            Una comunidad organizada en canales, pensada para aprender, compartir
            y conocer gente con tus mismos intereses.
        </p>

        <div class="features">
            <div class="feature-card">
                <div class="feature-tag">Comunidad</div>
                <div class="feature-title">Canales de charla</div>
                <p>
                    Salas de texto y voz para hablar, debatir ideas y compartir tu día
                    a día con otras personas.
                </p>
            </div>
            <div class="feature-card">
                <div class="feature-tag">Soporte</div>
                <div class="feature-title">Ayuda & dudas</div>
                <p>
                    Espacio para hacer preguntas, recibir ayuda de la comunidad y aprender
                    con ejemplos reales.
                </p>
            </div>
            <div class="feature-card">
                <div class="feature-tag">Proyectos</div>
                <div class="feature-title">Colaboraciones</div>
                <p>
                    Comparte tus proyectos, busca colaboradores o participa en ideas de otras
                    personas de la comunidad.
                </p>
            </div>
            <div class="feature-card">
                <div class="feature-tag">Eventos</div>
                <div class="feature-title">Actividades y novedades</div>
                <p>
                    Posibilidad de organizar eventos, retos, minijuegos o actividades dentro
                    del servidor.
                </p>
            </div>
        </div>
    </section>

    <!-- DISCORD -->
    <section id="discord">
        <h2 class="section-title">Únete al servidor de Discord</h2>
        <p class="section-sub">
            Pulsa el botón para entrar directamente a nuestro servidor oficial:
        </p>

        <a href="https://discord.gg/3FZEukEv" target="_blank" rel="noopener">
            <button class="btn-primary">
                <span>🚀</span> Entrar ahora a ArCLam
            </button>
        </a>

        <p style="margin-top: 10px; font-size: 12px; color: #a0a0a0;">
            Si el botón no funciona, copia este enlace manualmente:
            <code onclick="copyDiscordLink()" style="cursor:pointer;">https://discord.gg/3FZEukEv</code>
        </p>
    </section>

    <footer>
        <span>© <span id="year"></span> ArCLam. Todos los derechos reservados.</span>
        <span>Servidor Discord: <a href="https://discord.gg/3FZEukEv" target="_blank" rel="noopener">Unirme</a></span>
    </footer>
</main>

<script>
    // Año automático
    document.getElementById("year").textContent = new Date().getFullYear();

    // Scroll suave a secciones
    function scrollToSection(id) {
        const el = document.getElementById(id);
        if (!el) return;
        el.scrollIntoView({ behavior: "smooth", block: "start" });
    }

    // Copiar invitación de Discord
    function copyDiscordLink() {
        const link = "https://discord.gg/3FZEukEv";
        navigator.clipboard.writeText(link).then(() => {
            alert("Enlace copiado al portapapeles: " + link);
        }).catch(() => {
            alert("No se pudo copiar automáticamente. Copia este enlace: " + link);
        });
    }
</script>
</body>
</html>
