<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Plastic Heart Surgery</title>
    <style>
        /* Custom Font Registration */
        @font-face {
            font-family: 'Lyno Jean';
            src: url('fonts/lyno-jean.otf') format('opentype');
            font-weight: normal;
            font-style: normal;
        }

        :root {
            --bg-color: #0f0f0f;
            --text-color: #f0f0f0;
            --muted-color: #888888;
            --accent-color: #ffffff;
            --border-color: #222222;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            display: flex;
            min-height: 100vh;
            line-height: 1.6;
        }

        sidebar {
            width: 320px;
            background-color: var(--bg-color);
            border-right: 1px solid var(--border-color);
            padding: 40px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: fixed;
            height: 100vh;
            top: 0;
            left: 0;
            overflow-y: auto;
        }

        .site-title {
            font-family: 'Lyno Jean', sans-serif;
            font-size: 1.35rem;
            letter-spacing: 0.4em; /* Expanded letter spacing */
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8), 0 0 10px rgba(255, 255, 255, 0.1);
            margin-bottom: 40px;
            color: var(--accent-color);
        }

        .nav-columns {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .nav-column-item {
            font-family: 'Lyno Jean', sans-serif;
            font-size: 1.1rem;
            letter-spacing: 0.3em; /* Expanded letter spacing */
            text-shadow: 2px 2px 6px rgba(0, 0, 0, 0.8);
            color: var(--muted-color);
            text-decoration: none;
            transition: color 0.2s ease;
            cursor: pointer;
        }

        .nav-column-item:hover, .nav-column-item.active {
            color: var(--accent-color);
        }

        .sidebar-footer {
            font-size: 0.85rem;
            color: var(--muted-color);
            word-break: break-all;
            margin-top: 40px;
        }

        .sidebar-footer a {
            color: var(--text-color);
            text-decoration: none;
        }

        .sidebar-footer a:hover {
            text-decoration: underline;
        }

        main {
            margin-left: 320px;
            flex: 1;
            padding: 80px 60px;
            max-width: 900px;
        }

        section {
            margin-bottom: 120px;
        }

        h2 {
            font-family: 'Lyno Jean', sans-serif;
            font-size: 1.6rem;
            letter-spacing: 0.35em; /* Expanded letter spacing */
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8);
            margin-bottom: 24px;
            color: var(--accent-color);
        }

        p {
            color: var(--muted-color);
            margin-bottom: 16px;
            font-size: 1rem;
        }

        .artwork-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .artwork-item img {
            width: 100%;
            height: auto;
            border-radius: 4px;
            border: 1px solid var(--border-color);
        }

        .music-release {
            margin-bottom: 40px;
            background: #141414;
            border: 1px solid var(--border-color);
            padding: 24px;
            border-radius: 6px;
        }

        .music-release h3 {
            font-size: 1.1rem;
            color: var(--text-color);
            margin-bottom: 8px;
        }

        .music-release a.bandcamp-link {
            display: inline-block;
            margin-top: 12px;
            font-family: 'Lyno Jean', sans-serif;
            letter-spacing: 0.25em;
            text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.8);
            color: var(--text-color);
            font-size: 0.9rem;
            text-decoration: none;
            border-bottom: 1px solid var(--muted-color);
            padding-bottom: 2px;
        }

        .music-release a.bandcamp-link:hover {
            color: var(--accent-color);
            border-color: var(--accent-color);
        }

        .links-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        /* Applied custom font, letter spacing, and shadow to all URL links */
        .links-list a {
            font-family: 'Lyno Jean', sans-serif;
            font-size: 1.05rem;
            letter-spacing: 0.3em; /* 2-space wide tracking effect */
            text-shadow: 2px 2px 6px rgba(0, 0, 0, 0.8);
            color: var(--text-color);
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: opacity 0.2s;
        }

        .links-list a:hover {
            opacity: 0.7;
        }

        @media (max-width: 768px) {
            body {
                flex-direction: column;
            }
            sidebar {
                position: relative;
                width: 100%;
                height: auto;
                padding: 30px 20px;
                border-right: none;
                border-bottom: 1px solid var(--border-color);
            }
            main {
                margin-left: 0;
                padding: 40px 20px;
            }
        }
    </style>
</head>
<body>

    <sidebar>
        <div>
            <div class="site-title">Plastic Heart Surgery</div>
            <div class="nav-columns">
                <a onclick="scrollToSection('bio')" class="nav-column-item">01 / Bio</a>
                <a onclick="scrollToSection('artwork')" class="nav-column-item">02 / Artwork</a>
                <a onclick="scrollToSection('music')" class="nav-column-item">03 / Music</a>
                <a onclick="scrollToSection('links')" class="nav-column-item">04 / Links</a>
            </div>
        </div>
        <div class="sidebar-footer">
            <p style="margin-bottom: 4px; font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.05em;">Contact</p>
            <a href="mailto:plasticheartsurgery@gmail.com">plasticheartsurgery@gmail.com</a>
        </div>
    </sidebar>

    <main>
        <section id="bio">
            <h2>Bio</h2>
            <p>Multi-disciplinary artist, curator, and sound designer based in Toronto. Working across large-scale canvas painting, experimental electronic music, and hardware audio customisation.</p>
            <p>Practices explore themes relating to the natural world, structural mechanics, and the passage of time using mixed-media and abstraction.</p>
        </section>

        <section id="artwork">
            <h2>Artwork</h2>
            <p>Selected canvas pieces and visual projects.</p>
            <div class="artwork-grid">
                <div class="artwork-item">
                    <img src="images/And Now She Is a Monster - Brighter - 3000 x 3000.png" alt="And Now She Is a Monster">
                </div>
            </div>
        </section>

        <section id="music">
            <h2>Music</h2>
            <p>Electronic music releases, albums, and sound design projects.</p>
            
            <div style="margin-bottom: 40px;">
                <iframe style="border-radius:12px" src="https://open.spotify.com/embed/artist/5ZoUq3l7mN6OBgTMjpjfj7?utm_source=generator&theme=0" width="100%" height="352" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
            </div>

            <div class="music-release">
                <h3>And Now She Is a Monster</h3>
                <p>Experimental electronic release and audio project.</p>
                <a href="https://plasticheartsurgery.bandcamp.com/" class="bandcamp-link" target="_blank">Listen on Bandcamp ↗</a>
            </div>
        </section>

        <section id="links">
            <h2>Links & Socials</h2>
            <p>Find releases, audio projects, and updates across platforms.</p>
            <ul class="links-list">
                <li><a href="https://plasticheartsurgery.bandcamp.com/" target="_blank">Bandcamp ↗</a></li>
                <li><a href="https://open.spotify.com/artist/5ZoUq3l7mN6OBgTMjpjfj7" target="_blank">Spotify ↗</a></li>
                <li><a href="https://music.apple.com/ca/artist/plastic-heart-surgery/1539041975" target="_blank">Apple Music ↗</a></li>
                <li><a href="https://www.instagram.com/plastic.heart.surgery/" target="_blank">Instagram ↗</a></li>
                <li><a href="https://soundcloud.com" target="_blank">SoundCloud ↗</a></li>
                <li><a href="https://github.com/PlasticHeartSurgery" target="_blank">GitHub ↗</a></li>
            </ul>
        </section>
    </main>

    <script>
        function scrollToSection(id) {
            const element = document.getElementById(id);
            element.scrollIntoView({ behavior: 'smooth' });
            if (window.history.pushState) {
                window.history.pushState('', '', window.location.pathname);
            }
        }
    </script>

</body>
</html>
