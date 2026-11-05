<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Hamster Technologies</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

    <style>
        :root {
            --bg: #14161c;
            --surface: #1b1e27;
            --surface-raised: #20232e;
            --border: #2b2f3c;
            --border-bright: #3a3f50;
            --text: #e9eaef;
            --text-muted: #8b8fa3;
            --accent: #ffb300;
            --accent-dim: #7a5c17;
            --accent-teal: #3ddc97;
            --radius: 6px;
            --radius: 4px;
        }

        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            background:
                radial-gradient(circle at 15% 0%, rgba(255,179,0,0.06), transparent 40%),
                radial-gradient(circle at 85% 100%, rgba(61,220,151,0.05), transparent 40%),
                var(--bg);
            color: var(--text);
            font-family: 'Inter', sans-serif;
            line-height: 1.5;
        }

        a {
            color: inherit;
        }

        /* ---------- Header ---------- */
        header {
            border-bottom: 1px solid var(--border);
            padding: 1.6em 2em;
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 0.8em;
        }

        .brand {
            display: flex;
            flex-direction: column;
            gap: 0.15em;
        }

        .brand-eyebrow {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.7rem;
            letter-spacing: 0.18em;
            color: var(--accent);
            text-transform: uppercase;
        }

        h1 {
            font-family: 'Rajdhani', sans-serif;
            font-weight: 700;
            font-size: 2rem;
            letter-spacing: 0.02em;
            margin: 0;
            color: var(--text);
        }

        .status {
            display: flex;
            align-items: center;
            gap: 0.5em;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.78rem;
            color: var(--text-muted);
            letter-spacing: 0.05em;
        }

        .status-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--accent-teal);
            box-shadow: 0 0 8px var(--accent-teal);
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.35; }
        }

        /* ---------- Layout ---------- */
        main {
            padding: 2.5em 2em 3em;
            max-width: 1080px;
            margin: 0 auto;
        }

        .grid {
            display: grid;
            grid-template-columns: 1fr 1.3fr;
            gap: 1.5em;
            align-items: start;
        }

        @media (max-width: 760px) {
            .grid { grid-template-columns: 1fr; }
            header { padding: 1.4em 1.2em; }
            main { padding: 2em 1.2em 2.5em; }
        }

        .panel {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: var(--radius);
            position: relative;
            padding: 1.6em;
            margin-bottom: 1.5em;
        }

        /* HUD corner brackets — signature detail */
        .panel::before,
        .panel::after {
            content: "";
            position: absolute;
            width: 14px;
            height: 14px;
            border: 2px solid var(--accent);
            opacity: 0.55;
        }

        

        .panel::before {
            top: -1px;
            left: -1px;
            border-right: none;
            border-bottom: none;
        }

        .panel::after {
            bottom: -1px;
            right: -1px;
            border-left: none;
            border-top: none;
        }

        .panel-title {
            font-family: 'Rajdhani', sans-serif;
            font-weight: 600;
            font-size: 1.05rem;
            letter-spacing: 0.06em;
            text-transform: uppercase;
            color: var(--text);
            margin: 0 0 0.3em;
        }

        .panel-sub {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.75rem;
            color: var(--text-muted);
            margin: 0 0 1.3em;
        }

        /* ---------- Accounts ---------- */
        .account-list {
            display: flex;
            flex-direction: column;
            gap: 0.6em;
        }

        .account-link {
            display: flex;
            align-items: center;
            gap: 0.8em;
            padding: 0.85em 1em;
            background: var(--surface-raised);
            border: 1px solid var(--border);
            border-radius: var(--radius);
            text-decoration: none;
            transition: border-color 0.15s ease, transform 0.15s ease;
        }

        .account-link:hover,
        .account-link:focus-visible {
            border-color: var(--accent);
            transform: translateX(3px);
            outline: none;
        }

        .account-icon {
            width: 20px;
            height: 20px;
            flex-shrink: 0;
            color: var(--accent-teal);
        }

        .account-meta {
            display: flex;
            flex-direction: column;
            line-height: 1.25;
        }

        .account-name {
            font-weight: 600;
            font-size: 0.92rem;
        }

        .account-handle {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.75rem;
            color: var(--text-muted);
        }

        /* ---------- Specs & Settings ---------- */
        .spec-list {
            display: flex;
            flex-direction: column;
        }

        .spec-row {
            display: grid;
            grid-template-columns: 130px 1fr;
            gap: 1em;
            padding: 0.75em 0;
            border-bottom: 1px solid var(--border);
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
        }

        .spec-row:last-child {
            border-bottom: none;
        }

        .spec-label {
            color: var(--text-muted);
            letter-spacing: 0.04em;
            text-transform: uppercase;
            font-size: 0.72rem;
            align-self: center;
        }

        .spec-value {
            color: var(--text);
        }

        .spec-value .highlight {
            color: var(--accent);
        }

        ul {
            margin: 0;
            padding-left: 1.2em;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
        }

        ul li {
            padding: 0.4em 0;
            border-bottom: 1px solid var(--border);
        }

        ul li:last-child {
            border-bottom: none;
        }

        footer {
            text-align: center;
            padding: 1.5em;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.72rem;
            color: var(--text-muted);
            letter-spacing: 0.05em;
        }
    </style>
</head>
<body>

    <header>
        <div>
            <span class="brand-eyebrow"></span>
            <h1>Welcome to Hamster Technologies</h1>
        </div>
    </header>

    <main>

        <!-- Accounts Section -->
        <div class="panel">
            <h2 class="panel-title">My Account and Settings</h2>
            <p class="panel-sub">All my accounts will be here.</p>
            <div class="account-list">
                <a href="https://steamcommunity.com/id/199kbtw/" target="_blank" class="account-link">
                    <span class="account-name">Steam</span>
                </a>
                <a href="https://x.com/199kbtw" target="_blank" class="account-link">
                    <span class="account-name">X / Twitter</span>
                </a>
                <a href="https://www.twitch.tv/199kbtw" target="_blank" class="account-link">
                    <span class="account-name">Twitch</span>
                </a>
            </div>
        </div>

        <!-- PC Specs Section -->
        <div class="panel">
            <h2 class="panel-title">My Computer Specs</h2>
            <p class="panel-sub">Here are the specifications of my computer:</p>
            <ul>
                <li>CPU: AMD Ryzen 5 5500</li>
                <li>GPU: Nvidia GeForce GTX 1650</li>
                <li>Motherboard: TUF Gaming B550-Plus WiFi II</li>
                <li>Memory: 16GB DDR4</li>
                <li>Storage: 1TB SSD</li>
            </ul>
        </div>

        <!-- CS2 Settings Section -->
        <div class="panel">
            <h2 class="panel-title">Counter-Strike 2 Settings</h2>
            <p class="panel-sub">Here are my settings for Counter-Strike 2:</p>
            <ul>
                <li>Resolution: 1280×960</li>
                <li>Aspect Ratio: 4:3</li>
                <li>Refresh Rate: 165Hz</li>
                <li>Mouse Sensitivity: 0.79</li>
                <li>Crosshair Code: CSGO-TNmTC-u6ejq-iLrnr-iHNxu-UJAfD</li>
                <li>Key Bindings: Custom</li>
            </ul>
        </div>

        <! -- Daily Routine Section -->
        <div class="panel">
            <h2 class="panel-title">My Daily Routine</h2>
            <p class="panel-sub">Here is my daily routine:</p>
            <ul>
                <li>Wake up
                </li>Goon
                <li>Discord and check messages or notifications
                </li>
                <li>Game 
                </li>Programming or coding
                <li>Sleep
            </ul>
        </div>

        

    </main>

    <footer>
        Built by Hamster Technologies. All rights reserved. &copy; 2026
    </footer>

</body>
</html>
