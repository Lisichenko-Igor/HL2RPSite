<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>HL2RP | Ваш проект</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description" content="HL2RP сервер Garry's Mod — атмосфера City 17, авторские системы и проработанный лор.">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap" rel="stylesheet">

    <style>
        :root {
            --bg: #050608;
            --bg-alt: #0c1016;
            --accent: #ffb437;
            --accent-soft: #ffd987;
            --accent-secondary: #5ec3ff;
            --text: #f5f5f5;
            --muted: #a0a5b0;
            --border: rgba(255,255,255,0.06);
        }

        * {
            box-sizing: border-box;
        }

        html, body {
            margin: 0;
            padding: 0;
            background: radial-gradient(circle at top, #101623 0, #050608 55%);
            color: var(--text);
            font-family: "Roboto", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
        }

        body {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        a {
            color: var(--accent-secondary);
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        /* Шапка */

        header {
            position: sticky;
            top: 0;
            z-index: 10;
            backdrop-filter: blur(12px);
            background: linear-gradient(to bottom, rgba(4,6,10,0.9), rgba(4,6,10,0.7));
            border-bottom: 1px solid var(--border);
        }

        .nav {
            max-width: 1120px;
            margin: 0 auto;
            padding: 10px 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo-block {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-mark {
            width: 34px;
            height: 34px;
            border-radius: 8px;
            background: radial-gradient(circle at 30% 20%, #ffffff, #ffb547 40%, #e07023 80%);
            box-shadow:
                0 0 20px rgba(255,180,70,0.6),
                0 0 40px rgba(255,120,40,0.35);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 900;
            font-size: 16px;
            border: 1px solid rgba(0,0,0,0.7);
        }

        .logo-mark span {
            text-shadow: 0 0 6px rgba(0,0,0,0.9);
        }

        .logo-text-main {
            font-weight: 800;
            font-size: 18px;
            letter-spacing: 0.08em;
            text-transform: uppercase;
        }

        .logo-text-sub {
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 0.16em;
            color: var(--muted);
        }

        .nav-links {
            display: flex;
            gap: 18px;
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 0.12em;
        }

        .nav-links a {
            color: var(--muted);
            position: relative;
        }

        .nav-links a::after {
            content: "";
            position: absolute;
            left: 0;
            bottom: -4px;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--accent), var(--accent-secondary));
            transition: width 0.18s ease-out;
        }

        .nav-links a:hover {
            color: var(--text);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero */

        .hero {
            max-width: 1120px;
            margin: 0 auto;
            padding: 40px 20px 30px;
            display: grid;
            grid-template-columns: minmax(0, 1.5fr) minmax(0, 1.2fr);
            gap: 40px;
            align-items: center;
        }

        .hero-title {
            font-size: clamp(30px, 3.2vw, 40px);
            font-weight: 900;
            line-height: 1.1;
            text-transform: uppercase;
            letter-spacing: 0.08em;
        }

        .hero-title span {
            color: var(--accent);
        }

        .hero-subtitle {
            margin-top: 12px;
            font-size: 14px;
            color: var(--muted);
            max-width: 520px;
        }

        .hero-tags {
            margin-top: 16px;
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tag {
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 0.16em;
            padding: 4px 8px;
            border-radius: 999px;
            border: 1px solid rgba(255,255,255,0.08);
            background: rgba(14,18,26,0.8);
        }

        .tag--accent {
            border-color: rgba(255,180,55,0.8);
            color: var(--accent-soft);
        }

        .hero-cta {
            margin-top: 22px;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .btn {
            border-radius: 999px;
            border: none;
            cursor: pointer;
            font-size: 13px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.16em;
            padding: 10px 20px;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: transform 0.12s ease-out, box-shadow 0.12s ease-out, background 0.12s ease-out;
        }

        .btn-primary {
            color: #000;
            background: radial-gradient(circle at 20% 0, #fff5d9, #ffb437 38%, #e07124 82%);
            box-shadow:
                0 0 30px rgba(255,180,55,0.55),
                0 0 60px rgba(255,120,40,0.35);
        }

        .btn-primary:hover {
            transform: translateY(-1px);
            box-shadow:
                0 0 38px rgba(255,180,55,0.85),
                0 0 70px rgba(255,120,40,0.55);
        }

        .btn-outline {
            color: var(--accent-secondary);
            background: transparent;
            border: 1px solid rgba(94,195,255,0.7);
        }

        .btn-outline:hover {
            background: rgba(20,30,45,0.9);
            transform: translateY(-1px);
        }

        .btn small {
            font-size: 10px;
            text-transform: none;
            letter-spacing: normal;
            opacity: 0.8;
        }

        .hero-info {
            margin-top: 18px;
            font-size: 12px;
            color: var(--muted);
        }

        .hero-info strong {
            color: var(--accent-soft);
        }

        .hero-panel {
            position: relative;
            border-radius: 16px;
            padding: 16px;
            background: radial-gradient(circle at 0 0,#1d2333,#090c10 60%);
            border: 1px solid var(--border);
            box-shadow:
                0 0 40px rgba(0,0,0,0.9),
                0 0 60px rgba(6,10,18,0.9);
            overflow: hidden;
        }

        .hero-panel::before {
            content: "";
            position: absolute;
            inset: -1px;
            border-radius: inherit;
            border: 1px solid rgba(94,195,255,0.15);
            pointer-events: none;
        }

        .hero-panel-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
        }

        .hero-panel-title {
            font-size: 13px;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            color: var(--muted);
        }

        .hero-panel-status {
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 0.18em;
            color: var(--accent-secondary);
        }

        .hero-panel-grid {
            display: grid;
            grid-template-columns: repeat(2,minmax(0,1fr));
            gap: 10px;
        }

        .stat-card {
            padding: 10px 10px 8px;
            border-radius: 10px;
            border: 1px solid var(--border);
            background: rgba(4,6,10,0.8);
        }

        .stat-label {
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 0.16em;
            color: var(--muted);
            margin-bottom: 4px;
        }

        .stat-value {
            font-size: 16px;
            font-weight: 700;
        }

        .stat-value span {
            color: var(--accent-soft);
        }

        .stat-note {
            margin-top: 2px;
            font-size: 10px;
            color: var(--muted);
        }

        .hero-panel-footer {
            margin-top: 12px;
            padding-top: 8px;
            border-top: 1px solid rgba(255,255,255,0.03);
            font-size: 11px;
            color: var(--muted);
            display: flex;
            justify-content: space-between;
            gap: 12px;
        }

        .ip-highlight {
            font-family: "Consolas","Courier New",monospace;
            font-size: 12px;
            color: var(--accent-secondary);
        }

        /* Основные блоки */

        main {
            flex: 1 0 auto;
        }

        .section {
            max-width: 1120px;
            margin: 0 auto;
            padding: 12px 20px 32px;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            margin-bottom: 14px;
        }

        .section-title {
            font-size: 16px;
            text-transform: uppercase;
            letter-spacing: 0.18em;
        }

        .section-subtitle {
            font-size: 12px;
            color: var(--muted);
        }

        .grid-3 {
            display: grid;
            grid-template-columns: repeat(3,minmax(0,1fr));
            gap: 12px;
        }

        .card {
            position: relative;
            border-radius: 12px;
            padding: 12px;
            background: rgba(6,9,14,0.9);
            border: 1px solid var(--border);
            overflow: hidden;
        }

        .card::before {
            content: "";
            position: absolute;
            inset: 0;
            background: radial-gradient(circle at top left,rgba(255,180,70,0.07),transparent 60%);
            opacity: 0.7;
            pointer-events: none;
        }

        .card-title {
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 0.12em;
            margin-bottom: 4px;
        }

        .card-text {
            font-size: 13px;
            color: var(--muted);
        }

        .pill {
            display: inline-block;
            margin-top: 6px;
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 0.16em;
            color: var(--accent-secondary);
        }

        .two-column {
            display: grid;
            grid-template-columns: minmax(0,1.2fr) minmax(0,1fr);
            gap: 16px;
        }

        .list {
            list-style: none;
            padding: 0;
            margin: 0;
            font-size: 13px;
            color: var(--muted);
        }

        .list li {
            position: relative;
            padding-left: 16px;
            margin-bottom: 6px;
        }

        .list li::before {
            content: "▸";
            position: absolute;
            left: 0;
            top: 0;
            color: var(--accent);
            font-size: 10px;
        }

        .box {
            border-radius: 12px;
            padding: 12px;
            border: 1px dashed rgba(255,255,255,0.12);
            background: rgba(7,10,16,0.85);
            font-size: 13px;
            color: var(--muted);
        }

        .socials {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 6px;
        }

        .social-link {
            font-size: 12px;
            padding: 6px 10px;
            border-radius: 999px;
            border: 1px solid rgba(255,255,255,0.16);
            background: rgba(8,12,20,0.85);
        }

        /* Подвал */

        footer {
            border-top: 1px solid var(--border);
            background: #050608;
            padding: 12px 20px 14px;
            font-size: 11px;
            color: var(--muted);
        }

        .footer-inner {
            max-width: 1120px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 6px;
        }

        @media (max-width: 900px) {
            .hero {
                grid-template-columns: minmax(0,1fr);
                gap: 26px;
            }
            .hero-panel {
                order: -1;
            }
            .grid-3 {
                grid-template-columns: repeat(2,minmax(0,1fr));
            }
            .two-column {
                grid-template-columns: minmax(0,1fr);
            }
        }

        @media (max-width: 640px) {
            .nav-links {
                display: none;
            }
            .hero {
                padding-top: 28px;
            }
            .grid-3 {
                grid-template-columns: minmax(0,1fr);
            }
        }
    </style>
</head>
<body>

<header>
    <nav class="nav">
        <div class="logo-block">
            <div class="logo-mark"><span>C17</span></div>
            <div>
                <div class="logo-text-main">HL2RP PROJECT</div>
                <div class="logo-text-sub">CITY 17 ROLEPLAY SERVER</div>
            </div>
        </div>
        <div class="nav-links">
            <a href="#about">о проекте</a>
            <a href="#features">особенности</a>
            <a href="#join">как зайти</a>
            <a href="#community">сообщество</a>
        </div>
    </nav>
</header>

<main>
    <!-- HERO -->
    <section class="hero">
        <div>
            <div class="hero-title">
                Добро пожаловать в <span>City 17</span><br>
                ваш HL2RP проект
            </div>
            <div class="hero-subtitle">
                Атмосферный Half-Life 2 RolePlay сервер на Garry's Mod с авторскими системами,
                кастомным HUD, Deep RP и вниманием к деталям лора.
            </div>

            <div class="hero-tags">
                <div class="tag tag--accent">HL2RP</div>
                <div class="tag">Собственный HUD</div>
                <div class="tag">Alliance Scanner</div>
                <div class="tag">CID &amp; PlayTime</div>
            </div>

            <div class="hero-cta">
                <button class="btn btn-primary" onclick="navigator.clipboard && navigator.clipboard.writeText('xxx.xxx.xxx.xxx:27015')">
                    Подключиться к серверу
                    <small>IP: XXX.XXX.XXX.XXX:27015</small>
                </button>
                <a href="#join" class="btn btn-outline">
                    Инструкция по входу
                </a>
            </div>

            <div class="hero-info">
                <strong>Совместимость:</strong> Garry's Mod, контент HL2/EP1/EP2. <br>
                <strong>Режим:</strong> Half-Life 2 RolePlay, коллективные сюжетные линии.
            </div>
        </div>

        <div class="hero-panel">
            <div class="hero-panel-header">
                <div class="hero-panel-title">C17 CITY GRID</div>
                <div class="hero-panel-status">ONLINE</div>
            </div>
            <div class="hero-panel-grid">
                <div class="stat-card">
                    <div class="stat-label">Игроков онлайн</div>
                    <div class="stat-value"><span>12</span> / 64</div>
                    <div class="stat-note">* примерные данные, можно привязать к GameTracker / API</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Средний playtime</div>
                    <div class="stat-value">18 <span>ч.</span></div>
                    <div class="stat-note">Собственная система HL2RP_PlayTime (SQLite)</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Фракции</div>
                    <div class="stat-value">Альянс / ГСР / Сопротивление</div>
                    <div class="stat-note">Гибкая система категорий и CID</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Сезон</div>
                    <div class="stat-value"><span>1</span> / Лор-сетка</div>
                    <div class="stat-note">Заводы, подземка, рейды на слумы</div>
                </div>
            </div>
            <div class="hero-panel-footer">
                <div>IP сервера:<br><span class="ip-highlight">XXX.XXX.XXX.XXX:27015</span></div>
                <div>Steam-группа / Discord:<br><span class="ip-highlight">ссылки ниже</span></div>
            </div>
        </div>
    </section>

    <!-- О ПРОЕКТЕ -->
    <section class="section" id="about">
        <div class="section-header">
            <div class="section-title">О проекте</div>
            <div class="section-subtitle">Коротко о том, что делает сервер уникальным</div>
        </div>
        <div class="grid-3">
            <div class="card">
                <div class="card-title">Атмосферный HL2RP</div>
                <div class="card-text">
                    Проработка окружения, ambient‑звуки, визуальный стиль в духе оригинальной Half‑Life 2.
                    Лор‑сетка, опирающаяся на канон, но с авторскими ответвлениями.
                </div>
                <div class="pill">City 17 / Nova Prospekt / Outlands</div>
            </div>
            <div class="card">
                <div class="card-title">Системы игрока</div>
                <div class="card-text">
                    Диэгетический HUD, CID‑система, AllianceID, кастомный чат с сообщениями над головой,
                    система PlayTime и гибкие категории профессий.
                </div>
                <div class="pill">HUD / CID / PlayTime</div>
            </div>
            <div class="card">
                <div class="card-title">Фракции и роли</div>
                <div class="card-text">
                    ГСР, Сопротивление, Гражданские и особые позиции.
                    Сбалансированные условия игры, понятные правила взаимодействия и эскалации.
                </div>
                <div class="pill">Roleplay First</div>
            </div>
        </div>
    </section>

    <!-- ОСОБЕННОСТИ / ЛОР -->
    <section class="section" id="features">
        <div class="section-header">
            <div class="section-title">Особенности</div>
            <div class="section-subtitle">Техническая часть и геймплей</div>
        </div>
        <div class="two-column">
            <div>
                <h3 style="margin:2px 0 8px;font-size:14px;">Технические фичи</h3>
                <ul class="list">
                    <li>Кастомный диэгетический HUD с эффектом параллакса, повреждения,heartbeat, анимацией спавна.</li>
                    <li>Голограмма над игроком: ник, профа, CID/AllianceID с цветом по категории.</li>
                    <li>Собственная система PlayTime на SQLite (hl2rp_playtime) с ULX‑командой addtime.</li>
                    <li>Кастомный чат: фильтры (IC/OOC/TEAM/System), лог, всплывающие реплики над головой.</li>
                    <li>Поддержка DarkRP переменных (job, money, salary) и RPExtraTeams‑категорий.</li>
                </ul>

                <h3 style="margin:12px 0 8px;font-size:14px;">Геймплей и RP</h3>
                <ul class="list">
                    <li>Жёсткий, но понятный RP‑регламент: escalation ladder, правила задержаний и допросов.</li>
                    <li>Постоянные сюжетные ивенты: рейды, переброски, подпольные операции.</li>
                    <li>Система заявок на Whitelist‑роли (OTA, командование, спец‑персонажи).</li>
                </ul>
            </div>
            <div>
                <div class="box">
                    <strong>Сеттинг проекта (пример):</strong><br><br>
                    После событий оригинальной Half‑Life 2, но до окончательного падения Альянса.
                    Город‑17 живёт в режиме повышенного контроля, Сопротивление усиливает деятельность в
                    промзоне и канализации, гражданские балансируют между выживанием и лояльностью.<br><br>
                    Здесь можно написать короткий лор проекта или его уникальный хронологический отрезок.
                </div>
            </div>
        </div>
    </section>

    <!-- КАК ЗАЙТИ -->
    <section class="section" id="join">
        <div class="section-header">
            <div class="section-title">Как зайти и начать игру</div>
            <div class="section-subtitle">Пошаговая инструкция для новых игроков</div>
        </div>
        <div class="two-column">
            <div>
                <ol class="list" style="counter-reset:step;">
                    <li style="list-style:none;padding-left:0;">
                        <strong>1. Установите Garry's Mod и контент HL2/EP1/EP2</strong><br>
                        Рекомендуется наличие Half‑Life 2, Episode One и Episode Two для корректного отображения моделей и текстур.
                    </li>
                    <li style="list-style:none;padding-left:0;margin-top:6px;">
                        <strong>2. Подключитесь по IP</strong><br>
                        Откройте консоль (`~`) и введите:<br>
                        <code>connect XXX.XXX.XXX.XXX:27015</code>
                    </li>
                    <li style="list-style:none;padding-left:0;margin-top:6px;">
                        <strong>3. Ознакомьтесь с правилами</strong><br>
                        Перед игрой прочитайте правила проекта на форуме или в Discord. Нарушение базовых пунктов приводит к быстрому наказанию.
                    </li>
                    <li style="list-style:none;padding-left:0;margin-top:6px;">
                        <strong>4. Подайте заявку (если требуется)</strong><br>
                        На whitelist‑фракции (OTA, командование, особые роли) действуют заявки через форум/Discord.
                    </li>
                </ol>
            </div>
            <div>
                <div class="box">
                    <strong>IP сервера Garry's Mod:</strong><br>
                    <span class="ip-highlight">XXX.XXX.XXX.XXX:27015</span><br><br>
                    <strong>Коллекция Workshop:</strong><br>
                    <a href="#" target="_blank">Ссылка на коллекцию контента (Workshop)</a><br><br>
                    <strong>Форум / сайт:</strong><br>
                    <a href="#" target="_blank">forum.your-project.net</a> — место для гайдов, жалоб и заявок.
                </div>
            </div>
        </div>
    </section>

    <!-- СОЦИАЛКИ -->
    <section class="section" id="community">
        <div class="section-header">
            <div class="section-title">Сообщество</div>
            <div class="section-subtitle">Где нас найти и как связаться с администрацией</div>
        </div>
        <div class="two-column">
            <div>
                <div class="card">
                    <div class="card-title">Наши площадки</div>
                    <div class="card-text">
                        Основная коммуникация ведётся через Discord и Steam‑группу. Следите за анонсами и ивентами,
                        предлагайте идеи по развитию проекта, участвуйте в обсуждении лора и механик.
                    </div>
                    <div class="socials">
                        <a class="social-link" href="#" target="_blank">Discord сервера</a>
                        <a class="social-link" href="#" target="_blank">Steam‑группа</a>
                        <a class="social-link" href="#" target="_blank">VK / Telegram‑канал</a>
                    </div>
                </div>
            </div>
            <div>
                <div class="card">
                    <div class="card-title">Контакты администрации</div>
                    <div class="card-text">
                        <ul class="list">
                            <li>Технические вопросы и баг‑репорты — <strong>@Ваш_Dev</strong> (Discord).</li>
                            <li>Вопросы по банам и апелляциям — раздел на форуме или тикет в Discord.</li>
                            <li>Предложения по лору и ивентам — отдельный канал для обсуждения.</li>
                        </ul>
                    </div>
                    <div class="pill">Админ‑команда в онлайне каждый день</div>
                </div>
            </div>
        </div>
    </section>
</main>

<footer>
    <div class="footer-inner">
        <div>© <span id="year"></span> Ваш HL2RP проект. Неофициальный фан‑сервер во вселенной Half‑Life 2.</div>
        <div>Half‑Life 2 и связанные материалы принадлежат Valve Corporation.</div>
    </div>
</footer>

<script>
    // год в подвале
    document.getElementById('year').textContent = new Date().getFullYear();
</script>

</body>
</html>
