<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Animated Website</title>
    <style>
        :root {
            --color-bg: #f4f4f9;
            --color-card: #fff;
            --color-text: #1cc3c9;
            --color-bg: #f4f4f9;
            --color-nav: #1cc3c9;
            --color-accent: #40916c;
            --color-shadow: rgba(60,60,60,0.07);
            --color-toggle: #222;
            --color-toggle-bg: #e2e2e2;
        }
        [data-theme='dark'] {
            --color-bg: #181926;
            --color-card: #232946;
            --color-text: #f4f4f9;
            --color-nav: #181926;
            --color-accent: #21c088;
            --color-shadow: rgba(200,200,220,0.07);
            --color-toggle: #f4f4f9;
            --color-toggle-bg: #353552;
        }
        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            margin: 0;
            background: var(--color-bg);
            color: var(--color-text);
            transition: background 0.4s, color 0.3s;
        }
        a.instagram-link {
    color: white;
    text-decoration: none;
}
        header {
    position: sticky;
    top: 0;
    z-index: 20;
    background: var(--color-nav);
    color: #fff;
    padding: 22px 0 16px 0;
    text-align: center;
    /* Remove box-shadow to avoid the border effect */
    box-shadow: none;
    transition: opacity 0.6s, transform 0.6s, background 0.4s, color 0.4s;
}

        header.fade {
    opacity: 0;
    pointer-events: none;
    transform: translateY(-50px);
}
        nav ul {
            margin: 19px 0 0 0;
            padding: 0;
            list-style: none;
        }
        nav ul li {
            display: inline-block;
            margin: 0 25px;
            transition: transform 0.22s;
        }
        nav ul li a {
            color: #fff;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.08em;
            padding-bottom: 2px;
            border-bottom: 2px solid transparent;
            transition: color 0.2s, border 0.2s;
        }
        nav ul li a:hover, nav ul li a:focus {
            color: var(--color-accent);
            border-bottom: 2px solid var(--color-accent);
        }
        #toggle-theme-btn {
            position: absolute;
            right: 30px;
            top: 25px;
            background: var(--color-toggle-bg);
            border: none;
            border-radius: 40px;
            cursor: pointer;
            padding: 7px 11px;
            display: flex;
            align-items: center;
            transition: background 0.3s;
            box-shadow: 0 2px 8px 0 var(--color-shadow);
        }
        #toggle-theme-btn:active {
            scale: 0.9;
        }
        .toggle-icon {
            font-size: 1.37em;
            color: var(--color-toggle);
            transition: color 0.4s;
        }
        main {
            padding: 37px 8% 10px 8%;
        }
        section {
            background: var(--color-card);
            box-shadow: 0 5px 32px -12px var(--color-shadow);
            border-radius: 14px;
            margin-bottom: 28px;
            padding: 38px 25px 26px 25px;
            animation: fadein 1.1s;
            transition: background 0.3s, color 0.3s;
        }
        section h2 {
            margin-top: 0;
            color: var(--color-accent);
            letter-spacing: 1px;
            animation: slidein 0.6s;
        }
        section p, section ul {
            line-height: 1.7;
        }
        section ul li {
            transition: color 0.2s, margin-left 0.25s;
        }
        section ul li:hover { color: var(--color-accent); margin-left: 12px; }
        button {
            font-size: 1em;
            padding: 7px 22px;
            border-radius: 7px;
            border: none;
            background: var(--color-accent);
            color: #fff;
            font-weight: bold;
            letter-spacing: 1px;
            margin-top: 22px;
            cursor: pointer;
            transition: background 0.25s, transform 0.2s;
            box-shadow: 0 2px 16px -8px var(--color-shadow);
        }
        button:hover, button:focus {
            background: var(--color-nav);
            transform: translateY(-2px) scale(1.02);
        }
        footer {
            text-align: center;
            padding: 25px;
            background: var(--color-nav);
            color: #fff;
            font-size: 1em;
            box-shadow: 0 -1px 32px 0 var(--color-shadow);
            margin-top: 40px;
            letter-spacing: 1px;
        }
        @media (max-width: 800px) {
            main { padding: 8vw 3vw; }
            header { font-size: .95em; }
        }
        @media (max-width: 500px) {
            nav ul li { margin: 0 10px; }
            #toggle-theme-btn { right: 8px; top: 15px;}
        }
        @keyframes fadein {
            0% {opacity: 0; transform: translateY(40px);}
            100%{opacity: 1; transform: translateY(0);}
        }
        @keyframes slidein{
            from {opacity:0; transform: translateX(-70px);}
            to {opacity:1; transform: none;}
        }
        #site-title {
    transition: opacity 0.5s, transform 0.5s;
}
#site-title.fade {
    opacity: 0;
    transform: translateY(-25px);
}
a.instagram-link:active {
    color: red; /* keeps red color on click */
}
a.instagram-link:hover {
    /* Optional: keep white or add other effect */
    color: white;
   
}
    </style>
</head>
<body data-theme="light">
    <header>
        <h1 id="site-title">We're Hackerssssssss</h1>
        <button id="toggle-theme-btn" title="Toggle dark/light mode">
            <span class="toggle-icon" id="toggle-icon">&#9788;</span>
        </button>
        <nav>
            <ul>
                <li><a href="#home" onclick="scrollToSection('home')">Home</a></li>
                <li><a href="#about" onclick="scrollToSection('about')">About</a></li>
                <li><a href="#contact" onclick="scrollToSection('contact')">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section id="home">
            <h2>Home</h2>
            <p>Welcome! This interactive page switches between dark and light modes. Explore animated transitions and customized navigation.</p>
            <button onclick="showFunFact()">Click me for a fun surprise!</button>
            <p id="fun-fact" style="color:var(--color-nav);margin-top:20px;font-weight:bold;display:none;"></p>
        </section>
        <section id="about">
            <h2>About</h2>
            <p>This website template features smooth CSS animations, animated color transitions, and a responsive dark/light mode.&nbsp;Use it for portfolios, projects, or business profiles.</p>
            <ul>
                <li>Modern, responsive design</li>
                <li>Customizable color themes</li>
                <li>Smooth animated navigation</li>
                <li>Interactive demo features</li>
            </ul>
        </section>
        <section id="contact">
            <h2>Contact</h2>
            <ul>
                <li>Email: manikandankv653@email.com</li>
               <li>
                     Instagram: 
                    <a href="https://instagram.com/manikandankv._" target="_blank" rel="noopener">manikandankv._</a>
                </li>

                <li>LinkedIn: linkedin.com/in/yourprofile</li>
            </ul>
        </section>
    </main>
    <footer>
        &copy; 2025 Your Name. All rights reserved.
    </footer>
    <script>
        // Theme toggler
        const toggleBtn = document.getElementById('toggle-theme-btn');
        const icon = document.getElementById('toggle-icon');
        const body = document.body;
        let theme = localStorage.getItem('theme') || 'light';
        if (theme === 'dark') setTheme('dark');
        function setTheme(mode) {
            body.setAttribute('data-theme', mode);
            if (mode === 'dark') {
                icon.innerHTML = '&#9790;'; // moon icon
            } else {
                icon.innerHTML = '&#9788;'; // sun icon
            }
            localStorage.setItem('theme', mode);
        }
        toggleBtn.addEventListener('click', () => {
            theme = body.getAttribute('data-theme') === 'light' ? 'dark' : 'light';
            setTheme(theme);
        });

        // Animated scroll
        function scrollToSection(id) {
            let section = document.getElementById(id);
            section.scrollIntoView({ behavior: 'smooth' });
        }
        // Fun fact generator
        const facts = [
            "Did you know? HTML stands for HyperText Markup Language.",
            "CSS can be used to create animations without JavaScript!",
            "You can switch themes anytime with the toggle above.",
            "This template is 100% customizable—make it yours!",
            "JavaScript turns static pages into interactive experiences."
        ];
        function showFunFact() {
            const fact = facts[Math.floor(Math.random() * facts.length)];
            const el = document.getElementById('fun-fact');
            el.style.display = 'block';
            el.textContent = fact;
            el.style.opacity = 0;
            setTimeout(() => { el.style.transition = 'opacity 1s'; el.style.opacity = 1; }, 10);
        }
    </script>
    <script>
window.addEventListener('scroll', function(){
    const title = document.getElementById('site-title');
    // Adjust scroll threshold as needed (e.g. 60 pixels)
    if(window.scrollY > 60){
        title.classList.add('fade');
    } else{
        title.classList.remove('fade');
    }
});

window.addEventListener('scroll', function(){
    const header = document.querySelector('header');
    // Fade after scrolling more than 60px (adjust as needed)
    if(window.scrollY > 60){
        header.classList.add('fade');
    } else{
        header.classList.remove('fade');
    }
});
</script>

</body>
</html>
