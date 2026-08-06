
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dimitris Panagiotakopoulos | Academic Profile</title>
    <style>
        /* --- DESIGN SYSTEM: MIT MEDIA LAB STYLE (SHARP / GRID / BOLD) --- */
        :root {
            --bg: #ffffff;
            --fg: #000000;
            --accent: #0000ff; /* Lab Blue */
            --grid-color: #000000; /* Strict Black Lines */
            --subtle-bg: #f4f4f4;
            /* Typography */
            --font-head: "Helvetica Neue", Helvetica, Arial, sans-serif;
            --font-body: "Helvetica Neue", Helvetica, Arial, sans-serif;
            --font-mono: "Courier New", Courier, monospace;
            --pad: 24px;
        }
        [data-theme="dark"] {
            --bg: #111111;
            --fg: #ffffff;
            --accent: #4d4dff;
            --grid-color: #333333;
            --subtle-bg: #1a1a1a;
        }
        * { box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body {
            background-color: var(--bg);
            color: var(--fg);
            font-family: var(--font-body);
            line-height: 1.5;
            margin: 0;
            border-left: 1px solid var(--grid-color);
            border-right: 1px solid var(--grid-color);
            max-width: 1300px; /* Wide Lab Layout */
            margin: 0 auto;
        }
        a { color: inherit; text-decoration: none; cursor: pointer; }
        a:hover { color: var(--accent); }
        /* --- TYPOGRAPHY UTILS --- */
        h1, h2, h3, h4 { margin: 0; font-family: var(--font-head); font-weight: 700; letter-spacing: -0.02em; text-transform: uppercase; }
        .mono { font-family: var(--font-mono); font-size: 0.85rem; letter-spacing: 0.05em; text-transform: uppercase; }
        p { margin-bottom: 1rem; text-align: justify; font-size: 1rem; font-weight: 400; color: var(--fg); opacity: 0.9; }
        /* --- LAYOUT UTILS --- */
        .section-label {
            background: var(--fg);
            color: var(--bg);
            padding: 8px var(--pad);
            font-family: var(--font-mono);
            font-size: 0.8rem;
            text-transform: uppercase;
            display: block;
            border-bottom: 1px solid var(--grid-color);
        }
        /* --- HEADER --- */
        header {
            padding: 50px var(--pad);
            border-bottom: 1px solid var(--grid-color);
            position: relative;
        }
        h1 { font-size: clamp(2.5rem, 5vw, 4.5rem); line-height: 0.9; margin-bottom: 20px; }
        .header-meta { display: flex; gap: 20px; flex-wrap: wrap; color: var(--accent); font-weight: 700; }
        
        /* CONTROLS (BUTTONS) */
        .controls {
            position: absolute; top: 20px; right: 20px;
            display: flex; gap: 10px; z-index: 1000;
        }
        .btn-ctrl {
            background: var(--bg); border: 1px solid var(--grid-color);
            cursor: pointer; color: var(--fg); padding: 8px 12px;
            transition: all 0.2s; font-family: var(--font-mono); font-weight: bold;
            display: flex; align-items: center; justify-content: center;
        }
        .btn-ctrl:hover { background: var(--fg); color: var(--bg); }
        .icon { width: 20px; height: 20px; fill: currentColor; }

        /* --- STICKY NAV (Lab Style) --- */
        nav {
            position: sticky; top: 0; z-index: 1000;
            background: var(--bg);
            border-bottom: 1px solid var(--grid-color);
            display: flex; overflow-x: auto;
            white-space: nowrap;
        }
        .nav-item {
            padding: 15px 25px;
            font-family: var(--font-mono);
            font-weight: 700; font-size: 0.85rem;
            border-right: 1px solid var(--grid-color);
            color: var(--fg);
            transition: background 0.2s;
        }
        .nav-item:hover { background: var(--accent); color: white; }
        /* --- ABOUT (Split Grid) --- */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 350px;
            border-bottom: 1px solid var(--grid-color);
        }
        .about-text { padding: 40px var(--pad); border-right: 1px solid var(--grid-color); }
        .profile-img-container { position: relative; height: 100%; min-height: 350px; overflow: hidden; }
        .profile-img {
            width: 100%; height: 100%; object-fit: cover;
            filter: grayscale(100%);
            transition: filter 0.4s;
        }
        .profile-img:hover { filter: grayscale(0%); }
        /* --- PHD SECTION (Tech Box) --- */
        .phd-hero {
            display: grid;
            grid-template-columns: 1fr 1fr; /* Split Visual / Text */
            border-bottom: 1px solid var(--grid-color);
        }
        .anim-box {
            background: #000000; /* STRICT BLACK BACKGROUND */
            display: flex; align-items: center; justify-content: center;
            border-right: 1px solid var(--grid-color);
            min-height: 300px;
            overflow: hidden;
            position: relative;
        }
        .phd-info { padding: 40px var(--pad); display: flex; flex-direction: column; justify-content: center; }
        .phd-info h2 { font-size: 2rem; color: var(--accent); margin-bottom: 20px; line-height: 1.1; }
        .phd-quote { font-family: "Georgia", serif; font-style: italic; opacity: 0.8; padding-left: 20px; border-left: 3px solid var(--accent); }
        /* 4 Pillars Grid */
        .phd-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            border-bottom: 1px solid var(--grid-color);
        }
        .phd-col {
            padding: 25px;
            border-right: 1px solid var(--grid-color);
            text-align: center;
            transition: background 0.2s;
        }
        .phd-col:last-child { border-right: none; }
        .phd-col:hover { background: var(--subtle-bg); }
        .phd-icon { height: 40px; margin-bottom: 15px; color: var(--fg); }
        .phd-col h4 { margin-bottom: 10px; font-size: 0.9rem; color: var(--accent); }
        .phd-col p { font-size: 0.9rem; line-height: 1.4; margin: 0; }
        /* --- BENTO GRID (Themes & Art) --- */
        .bento-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            border-bottom: 1px solid var(--grid-color);
        }
        .project-card {
            border-right: 1px solid var(--grid-color);
            border-bottom: 1px solid var(--grid-color);
            display: flex; flex-direction: column;
            transition: background 0.2s;
            position: relative;
        }
        .project-card:hover { background: var(--subtle-bg); }
        /* Bento Logic */
        .card-large { grid-column: span 2; }
        
        .p-img {
            width: 100%; height: 240px; object-fit: cover;
            border-bottom: 1px solid var(--grid-color);
            filter: grayscale(100%);
            transition: filter 0.3s;
        }
        .project-card:hover .p-img { filter: grayscale(0%); }
        
        .p-content { padding: 25px; flex: 1; display: flex; flex-direction: column; }
        .p-tag { font-family: var(--font-mono); font-size: 0.75rem; color: var(--accent); margin-bottom: 8px; display: block; }
        .p-title { font-size: 1.3rem; margin-bottom: 10px; line-height: 1.1; }
        .p-desc { font-size: 0.9rem; margin-bottom: 20px; flex: 1; }
        .p-arrow { align-self: flex-end; font-size: 1.5rem; opacity: 0; transform: translateX(-10px); transition: all 0.3s; }
        .project-card:hover .p-arrow { opacity: 1; transform: translateX(0); }

        /* --- STRICT LISTS (CV Style) --- */
        .list-section { border-bottom: 1px solid var(--grid-color); }
        .list-row {
            display: flex;
            padding: 15px var(--pad);
            border-bottom: 1px solid var(--grid-color);
            align-items: baseline;
        }
        .list-row:last-child { border-bottom: none; }
        .list-row:hover { background: var(--subtle-bg); }
        
        .list-col-left {
            width: 140px; flex-shrink: 0;
            font-family: var(--font-mono); font-weight: 700; color: var(--accent);
        }
        .list-col-right { flex: 1; }
        .list-title { display: block; font-weight: 700; font-size: 1.05rem; margin-bottom: 4px; }
        .list-meta { font-size: 0.95rem; opacity: 0.9; }
        .pub-link { font-family: var(--font-mono); font-size: 0.75rem; color: var(--accent); margin-left: 10px; text-decoration: underline; }
        /* --- MOBILITY SECTION --- */
        .mobility-grid {
            display: grid;
            grid-template-columns: 1fr 350px;
            border-bottom: 1px solid var(--grid-color);
            min-height: 200px;
        }
        .mobility-content {
            border-right: 1px solid var(--grid-color);
            display: flex;
            align-items: center;
        }
        .mobility-img-box {
            position: relative;
            overflow: hidden;
            height: 100%;
            min-height: 250px;
        }
        .mobility-img {
            width: 100%; height: 100%; object-fit: cover;
            filter: grayscale(100%);
            transition: filter 0.4s;
        }
        .mobility-grid:hover .mobility-img { filter: grayscale(0%); }
        /* --- CONTACT & MAP --- */
        .contact-cta {
            padding: 30px var(--pad);
            border-bottom: 1px solid var(--grid-color);
            background: var(--subtle-bg);
            text-align: center;
        }
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr; /* Split 50/50 */
            border-bottom: 1px solid var(--grid-color);
        }
        .contact-details {
            padding: 40px var(--pad);
            border-right: 1px solid var(--grid-color);
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        .contact-list { list-style: none; padding: 0; margin: 0; }
        .contact-list li { margin-bottom: 20px; font-family: var(--font-mono); font-size: 0.95rem; }
        .contact-list strong { display: block; color: var(--accent); margin-bottom: 5px; text-transform: uppercase; font-family: var(--font-head); }
        
        .map-box {
            position: relative;
            height: 100%;
            min-height: 450px;
            background: #e5e5e5;
            overflow: hidden;
        }
                
        /* MODERN MAP STYLING */
        .map-frame {
            width: 100%; height: 100%; border: 0;
            /* Default Light Mode: High Contrast Grayscale */
            filter: grayscale(100%) contrast(1.1);
            transition: all 0.5s ease;
        }
                
        /* Dark Mode: Inverted Colors for "Night Map" effect */
        [data-theme="dark"] .map-frame {
            filter: grayscale(100%) invert(92%) contrast(1.2);
        }
        /* Hover: Restore Full Colors */
        .contact-grid:hover .map-frame { 
            filter: grayscale(0%) invert(0%) contrast(1); 
        }
        /* --- ANIMATIONS --- */
        .sensor-ring { animation: pulse-ring 3s infinite; }
        @keyframes pulse-ring { 0% { opacity: 0.5; stroke-width: 1; r: 30; } 50% { opacity: 1; stroke-width: 3; r: 32; } 100% { opacity: 0.5; stroke-width: 1; r: 30; } }
        /* --- FOOTER --- */
        footer { padding: 40px; text-align: center; font-family: var(--font-mono); font-size: 0.8rem; }
        /* --- RESPONSIVE --- */
        @media (max-width: 900px) {
            .about-grid { grid-template-columns: 1fr; }
            .about-text { border-right: none; border-bottom: 1px solid var(--grid-color); }
            .profile-img-container { height: 300px; }
            
            .phd-hero { grid-template-columns: 1fr; }
            .anim-box { border-right: none; border-bottom: 1px solid var(--grid-color); }
            
            .phd-grid { grid-template-columns: 1fr 1fr; }
            .phd-col { border-right: 1px solid var(--grid-color); border-bottom: 1px solid var(--grid-color); }
            .phd-col:nth-child(2n) { border-right: none; }
            
            .card-large { grid-column: span 1; }
            
            .list-row { flex-direction: column; }
            .list-col-left { margin-bottom: 5px; }
            .mobility-grid { grid-template-columns: 1fr; }
            .mobility-content { border-right: none; border-bottom: 1px solid var(--grid-color); }
            .mobility-img-box { height: 250px; }
            .contact-grid { grid-template-columns: 1fr; }
            .contact-details { border-right: none; border-bottom: 1px solid var(--grid-color); }
            .map-box { min-height: 300px; }
        }
        @media (max-width: 600px) { .phd-grid { grid-template-columns: 1fr; } .phd-col { border-right: none; } }
    </style>
</head>
<body>
    <header>
        <h1>Dimitris<br>Panagiotakopoulos</h1>
        <div class="header-meta mono">
            <span id="txt-h-rank">PHD CANDIDATE</span>
            <span>//</span>
            <span id="txt-h-uni">UNIVERSITY OF WEST ATTICA</span>
            <span>//</span>
            <span id="txt-h-loc">ATHENS, GREECE</span>
        </div>
        <div style="margin-top: 15px;" class="mono">
            <a href="mailto:dpanagiotakopoulos@uniwa.gr">dpanagiotakopoulos@uniwa.gr</a> | 
            <a href="https://scholar.google.com/citations?user=KTVlHPwAAAAJ&hl=en" target="_blank">Google Scholar</a> | 
            <a href="https://orcid.org/0000-0001-7087-772X" target="_blank">ORCID</a>
        </div>
        
        <div class="controls">
            <button class="btn-ctrl" id="lang-btn">GR</button>
            <button class="btn-ctrl" id="theme-btn" aria-label="Toggle Theme">
                <svg class="icon" viewBox="0 0 24 24"><path d="M12 2.25a.75.75 0 01.75.75v2.25a.75.75 0 01-1.5 0V3a.75.75 0 01.75-.75zM7.5 12a4.5 4.5 0 119 0 4.5 4.5 0 01-9 0zM18.894 6.166a.75.75 0 00-1.06-1.06l-1.591 1.59a.75.75 0 101.06 1.061l1.591-1.59zM21.75 12a.75.75 0 01-.75.75h-2.25a.75.75 0 010-1.5H21a.75.75 0 01.75.75zM17.834 18.894a.75.75 0 001.06-1.06l-1.59-1.591a.75.75 0 10-1.061 1.06l1.59 1.591zM12 18a.75.75 0 01.75.75V21a.75.75 0 01-1.5 0v-2.25A.75.75 0 0112 18zM7.758 17.303a.75.75 0 00-1.061-1.06l-1.591 1.59a.75.75 0 001.06 1.061l1.591-1.59zM6 12a.75.75 0 01-.75.75H3a.75.75 0 010-1.5h2.25A.75.75 0 016 12zM6.697 7.757a.75.75 0 001.06-1.06l-1.59-1.591a.75.75 0 00-1.061 1.06l1.59 1.591z" /></svg>
            </button>
        </div>
    </header>
    <nav>
        <a href="#about" class="nav-item" id="nav-1">About</a>
        <a href="#phd" class="nav-item" id="nav-2">Dissertation</a>
        <a href="#education" class="nav-item" id="nav-3">Education</a>
        <a href="#themes" class="nav-item" id="nav-4">Research Themes</a>
        <a href="#art" class="nav-item" id="nav-art">Art Portfolio</a>
        <a href="#projects" class="nav-item" id="nav-prj">Funded Projects</a>
        <a href="#publications" class="nav-item" id="nav-5">Publications</a>
        <a href="#activity" class="nav-item" id="nav-6">Activity</a>
        <a href="#contact" class="nav-item" id="nav-7">Contact</a>
    </nav>
    <main>
        <section id="about">
            <span class="section-label" id="lbl-1">01 // PROFILE</span>
            <div class="about-grid">
                <div class="about-text">
                    <p style="font-size: 1.3rem; font-weight: 700; margin-bottom: 20px;" id="txt-bio-1">
                        Dimitris Panagiotakopoulos is a Ph.D. Candidate and member of the "Design, Interior Architecture & Audiovisual Documentation" research laboratory at the University of West Attica, where he also serves as an Academic Fellow (Teaching Assistant).
                    </p>
                    <p id="txt-bio-2">
                        His research interests lie within the broader scope of multimedia science, focusing on interaction design and the production process. His doctoral thesis specifically explores <strong>Digital Scent Technology</strong> within the Metaverse, investigating how multisensory interfaces can enhance user experience.
                    </p>
                    <p id="txt-bio-3">
                        He has worked at the European Commission (DG DIGIT) in Brussels, and previously served as an editor and producer for television advertisements in the private sector in Milan, Italy. His background in Digital Humanities was established through internships at the University of Bologna (Department of History and Culture)—where he participated in the "BYZART" European research project—and the Ephorate of Palaeoanthropology and Speleology of the Hellenic Ministry of Culture.
                    </p>
                    <p id="txt-bio-4">
                        His academic background combines creative arts with advanced technology. He holds an Integrated Master in Audio Visual Arts from the Ionian University and an MSc in "Intelligent Packaging: New Technologies and Marketing" from the University of West Attica. Additionally, he attended the Master of Fine Arts (MFA) program at Cardiff Metropolitan University via the Erasmus+ program. He also holds a Certificate of Pedagogical and Teaching Competence, fully qualifying him to teach Art subjects in Primary and Secondary Education.
                    </p>
                </div>
                <div class="profile-img-container">
                    <img src="profile.jpg" alt="Dimitris Panagiotakopoulos" class="profile-img">
                </div>
            </div>
        </section>
        <section id="phd">
            <span class="section-label" id="lbl-2">02 // PHD DISSERTATION</span>
            <div class="phd-hero">
                <div class="anim-box">
                    <svg viewBox="0 0 400 300" width="100%" height="100%" preserveAspectRatio="xMidYMid slice">
                        <defs>
                            <pattern id="grid-pattern" width="40" height="40" patternUnits="userSpaceOnUse">
                                <path d="M 40 0 L 0 0 0 40" fill="none" stroke="#222" stroke-width="1"/>
                            </pattern>
                            <radialGradient id="sensor-glow" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
                                <stop offset="0%" stop-color="#4d4dff" stop-opacity="0.8"/>
                                <stop offset="100%" stop-color="#000" stop-opacity="0"/>
                            </radialGradient>
                            <linearGradient id="scent-trail" x1="0%" y1="100%" x2="0%" y2="0%">
                                <stop offset="0%" stop-color="#fff" stop-opacity="0"/>
                                <stop offset="50%" stop-color="#fff" stop-opacity="0.8"/>
                                <stop offset="100%" stop-color="#4d4dff" stop-opacity="1"/>
                            </linearGradient>
                        </defs>
                        <rect width="100%" height="100%" fill="url(#grid-pattern)" opacity="0.6" />
                        <g transform="translate(200, 150)">
                            <circle r="10" fill="none" stroke="#4d4dff" stroke-width="1" opacity="0">
                                <animate attributeName="r" values="30;120" dur="4s" repeatCount="indefinite" />
                                <animate attributeName="opacity" values="0.6;0" dur="4s" repeatCount="indefinite" />
                            </circle>
                            <circle r="10" fill="none" stroke="#4d4dff" stroke-width="1" opacity="0">
                                <animate attributeName="r" values="30;120" dur="4s" repeatCount="indefinite" begin="2s"/>
                                <animate attributeName="opacity" values="0.6;0" dur="4s" repeatCount="indefinite" begin="2s"/>
                            </circle>
                            <circle cx="0" cy="0" r="30" fill="none" stroke="#fff" stroke-width="2" class="sensor-ring"/>
                            <circle cx="0" cy="0" r="8" fill="#4d4dff" class="sensor-core">
                                <animate attributeName="opacity" values="0.5;1;0.5" dur="2s" repeatCount="indefinite"/>
                            </circle>
                            <circle r="3" fill="url(#scent-trail)" opacity="0">
                                <animateMotion path="M -80 100 Q -40 50 0 0" dur="3s" repeatCount="indefinite" />
                                <animate attributeName="opacity" values="0;1;0" dur="3s" repeatCount="indefinite" />
                            </circle>
                            <circle r="3" fill="url(#scent-trail)" opacity="0">
                                <animateMotion path="M 80 100 Q 40 50 0 0" dur="3.5s" repeatCount="indefinite" begin="0.5s"/>
                                <animate attributeName="opacity" values="0;1;0" dur="3.5s" repeatCount="indefinite" begin="0.5s"/>
                            </circle>
                            <circle r="2" fill="#fff" opacity="0">
                                <animateMotion path="M 0 120 L 0 0" dur="2.5s" repeatCount="indefinite" begin="1s"/>
                                <animate attributeName="opacity" values="0;1;0" dur="2.5s" repeatCount="indefinite" begin="1s"/>
                            </circle>
                        </g>
                    </svg>
                </div>
                <div class="phd-info">
                    <h2 id="txt-phd-title">Olfactory Metaverse Experience Design</h2>
                    <div class="phd-quote" id="txt-phd-quote">
                        "But when from a long-distant past nothing subsists... taste and smell alone... bear unfaltering... the vast structure of recollection." — Marcel Proust
                    </div>
                </div>
            </div>
            <div class="phd-grid">
                <div class="phd-col">
                    <svg class="phd-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><line x1="2" y1="12" x2="22" y2="12" stroke-dasharray="4 2"></line><circle cx="18" cy="12" r="3"></circle></svg>
                    <h4 class="mono" id="txt-phd-c1-t">THE SHIFT</h4>
                    <p id="txt-phd-c1-d">Transitioning from <strong>Techno-anosmia</strong> to the <strong>3rd Wave</strong> of digital scent, driven by Perceptual Engineering.</p>
                </div>
                <div class="phd-col">
                    <svg class="phd-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="8" cy="12" r="6"></circle><circle cx="16" cy="12" r="6"></circle></svg>
                    <h4 class="mono" id="txt-phd-c2-t">THE THEORY</h4>
                    <p id="txt-phd-c2-d">Defining <strong>Liminal Interaction</strong>: Scent as a connective tissue for <strong>Co-Reality</strong> between physical and digital worlds.</p>
                </div>
                <div class="phd-col">
                    <svg class="phd-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"></path></svg>
                    <h4 class="mono" id="txt-phd-c3-t">INNOVATION</h4>
                    <p id="txt-phd-c3-d">Introducing the <strong>OloMET Framework</strong> and the <strong>Spatial Scent GUI</strong> for 3D olfactory diffusion control.</p>
                </div>
                <div class="phd-col">
                    <svg class="phd-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>
                    <h4 class="mono" id="txt-phd-c4-t">ETHICS</h4>
                    <p id="txt-phd-c4-d">Proposal for a <strong>Ethical Design Framework</strong> for Neurorights, covering the legal gap in mental privacy.</p>
                </div>
            </div>
        </section>
        <section id="education">
            <span class="section-label" id="lbl-3">03 // EDUCATION</span>
            <div class="list-row">
                <div class="list-col-left">2020 - 2026</div>
                <div class="list-col-right">
                    <span class="list-title" id="edu-1-t">Ph.D. Candidate (8 EQF)</span>
                    <span class="list-meta" id="edu-1-d">Dept. of Graphic Design & Visual Communication, University of West Attica.<br><strong>Thesis:</strong> "Digital Scent Technology in Metaverse Environments"</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2023</div>
                <div class="list-col-right">
                    <span class="list-title" id="edu-2-t">Special Pedagogy Certification of Teaching Proficiency</span>
                    <span class="list-meta" id="edu-2-d">Ionian University.</span>
                </div>
            </div> 
            <div class="list-row">
                <div class="list-col-left">2018 - 2020</div>
                <div class="list-col-right">
                    <span class="list-title" id="edu-3-t">MSc in Intelligent Packaging: New Technologies & Marketing</span>
                    <span class="list-meta" id="edu-3-d">University of West Attica (90 ECTS, 7 EQF).</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2011 - 2017</div>
                <div class="list-col-right">
                    <span class="list-title" id="edu-4-t">Integrated Master in Audio Visual Arts</span>
                    <span class="list-meta" id="edu-4-d">Ionian University (300 ECTS, 7 EQF).</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2015</div>
                <div class="list-col-right">
                    <span class="list-title" id="edu-5-t">Erasmus+ (Master of Fine Arts Module)</span>
                    <span class="list-meta" id="edu-5-d">Cardiff Metropolitan University.</span>
                </div>
            </div>
        </section>
        <section id="awards">
            <span class="section-label" id="lbl-4">04 // AWARDS & SCHOLARSHIPS</span>
            <div class="list-row">
                <div class="list-col-left">2023</div>
                <div class="list-col-right">
                    <span class="list-title" id="aw-1-t">Most Popular Article Award</span>
                    <span class="list-meta" id="aw-1-d">Awarded by <em>IEEE IT Professional</em> for the article "Digital Scent Technology Toward the Internet of Senses and the Metaverse".</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2019 - 2024</div>
                <div class="list-col-right">
                    <span class="list-title" id="aw-2-t">Doctorate Scholarship</span>
                    <span class="list-meta" id="aw-2-d">Special Account for Research Funds (ELKE), University of West Attica.</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2016</div>
                <div class="list-col-right">
                    <span class="list-title" id="aw-3-t">Erasmus+ Scholarship for Traineeship</span>
                    <span class="list-meta" id="aw-3-d">University of Bologna, Italy (Digital Humanities).</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2015</div>
                <div class="list-col-right">
                    <span class="list-title" id="aw-4-t">Erasmus+ Scholarship for Studies</span>
                    <span class="list-meta" id="aw-4-d">Cardiff Metropolitan University, UK (Master of Fine Arts).</span>
                </div>
            </div>
        </section>
        <section id="teaching">
            <span class="section-label" id="lbl-5">05 // TEACHING EXPERIENCE</span>
            <div class="list-row">
                <div class="list-col-left">2020 - Pres.</div>
                <div class="list-col-right">
                    <span class="list-title" id="tea-1-t">Teaching Assistant (Academic Fellow)</span>
                    <span class="list-meta" id="tea-1-d">University of West Attica. Courses: 1) <em>Multimedia Graphic Design</em>, 2) <em>Digital Interactive Multimedia Applications</em></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2020 - Pres.</div>
                <div class="list-col-right">
                    <span class="list-title" id="tea-2-t">Mentoring & Thesis Supervision</span>
                    <span class="list-meta" id="tea-2-d">Master thesis Co-Supervisions & Mentoring programme, University of West Attica.</span>
                </div>
            </div>
        </section>
        <section id="mobility">
            <span class="section-label" id="lbl-6">06 // INTERNATIONAL MOBILITY</span>
            <div class="mobility-grid">
                <div class="mobility-content">
                    <div class="list-row" style="border-bottom: none; width: 100%; padding-left: 24px;">
                        <div class="list-col-left">2025</div>
                        <div class="list-col-right">
                            <span class="list-title" id="mob-1-t">Erasmus+ ICM – Visiting PhD Researcher</span>
                            <span class="list-meta" id="mob-1-d">Technical University of Moldova (UTM), Chișinău.</span>
                        </div>
                    </div>
                </div>
                <div class="mobility-img-box">
                    <img src="moldova.jpg" alt="Dimitris Panagiotakopoulos - Visiting PhD Researcher at Technical University of Moldova" class="mobility-img">
                </div>
            </div>
        </section>
        <section id="themes">
            <span class="section-label" id="lbl-7">07 // RESEARCH THEMES & CASE STUDIES</span>
            <div class="bento-grid">
                <div class="project-card card-large">
                    <img src="project8.jpg" alt="Sacred Futurism Art" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[ART / AI / THEOLOGY]</span>
                        <h3 class="p-title" id="pj-1-t">Sacred Futurism</h3>
                        <p class="p-desc" id="pj-1-d">
                            The project presents a series of artworks and their analysis under the theme of Sacred Futurism. It explores the contrast between the sacred and technology by depicting robots in the roles of traditional holy figures, rendered in a Byzantine style. Set against post-apocalyptic landscapes, the works address ecological destruction while suggesting that, in a dystopian future, robots may rebuild society based on ethical values and the protection of life. The analysis examines the relationship between religion, the metaverse, robotics, and artificial intelligence, discussing concepts such as transhumanism and "Robot Theology."
                        </p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card card-large">
                    <img src="project1.jpg" alt="Digital Scent" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[HCI / REVIEW]</span>
                        <h3 class="p-title" id="pj-2-t">Digital Scent Technology & IoS</h3>
                        <p class="p-desc" id="pj-2-d">Exploring multisensory interface technologies for HCI, focusing on digital scent. Reviews current electrical interfaces, chemical odor delivery, and the commercial potential of the Internet of Senses (IoS) and 6G infrastructure.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card card-large">
                    <img src="spatial-ui.jpg" alt="Spatial GUI" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[UX / PROTOTYPE]</span>
                        <h3 class="p-title" id="pj-3-t">Spatial User Interfaces</h3>
                        <p class="p-desc" id="pj-3-d">Developing 3D controls for olfactory diffusion in immersive environments. The project addresses the lack of visual tools for designing scent in the Metaverse.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="project2.jpg" alt="VR Public" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[VR / PUBLIC SECTOR]</span>
                        <h3 class="p-title" id="pj-4-t">METAVERSE in Public Sector</h3>
                        <p class="p-desc" id="pj-4-d">Examining the application of Virtual Reality in the public sector. Explores sensory enhancement (haptic, auditory, olfactory) to create immersive experiences.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="project3.jpg" alt="Erasmus" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[METAVERSE / EU]</span>
                        <h3 class="p-title" id="pj-5-t">Metaverse Erasmus Hub</h3>
                        <p class="p-desc" id="pj-5-d">A proposal to the European Commission for integrating metaverse technologies into Erasmus+. Enhances physical mobility via AI avatars.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="project4.jpg" alt="Education" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[CASE STUDY]</span>
                        <h3 class="p-title" id="pj-6-t">Metaverse in Education</h3>
                        <p class="p-desc" id="pj-6-d">Case study with 20 students using Spatial. Findings indicate increased creativity (50%) and interest in technology integration (70%).</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="project5.jpg" alt="Packaging" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[IOT / TOURISM]</span>
                        <h3 class="p-title" id="pj-7-t">INTELLIGENT Packaging</h3>
                        <p class="p-desc" id="pj-7-d">Exploring smart packaging as a key trend in tourism, blending physical and digital worlds via IoT, 5G, RFID, and NFC.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="project6.jpg" alt="Prinzhorn" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[VR / PSYCHOLOGY]</span>
                        <h3 class="p-title" id="pj-8-t">Prinzhorn Collection & VR</h3>
                        <p class="p-desc" id="pj-8-d">Study on psychiatric artworks (Heidelberg) to explore emotion elicitation and simulate psychosis in VR environments.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="project7.jpg" alt="Participatory" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[ETHICS / 5IR]</span>
                        <h3 class="p-title" id="pj-9-t">ETHICAL METAVERSE</h3>
                        <p class="p-desc" id="pj-9-d">Participatory Design (PD) as an ethical necessity for building an inclusive Metaverse. Rooted in the philosophy of Ubuntu.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="kafka.jpg" alt="Kafkaesque Labyrinth" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[HYPERTEXT / LITERATURE / ART]</span>
                        <h3 class="p-title" id="pj-10-t">KAFKAESQUE LABYRINTH</h3>
                        <p class="p-desc" id="pj-10-d">
                            Through an innovative educational approach to Kafka's work, hypertext fiction practices are employed. In search of the thread of interpretation, thoughts, experiences, and reflections are transformed into a creative artistic response. The interpretative process emerges as a field where art and technology intersect. <br><br> @ Panagiotakopoulos / Hyper-Kafka Memory Rooms
                        </p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="flox_box.jpg" alt="FLOQ BOX" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[AFFECTIVE COMPUTING / HOLOGRAPHY]</span>
                        <h3 class="p-title" id="pj-11-t">FLOQ BOX</h3>
                        <p class="p-desc" id="pj-11-d">
                            The Flow Box is inspired by the concept of "fluidity" in the modern world and explores human emotions. The device uses Affective Computing technologies to recognize the user's emotions, which it then metabolizes and represents through holographic simulation. With industrial materials (PVC, metal) and sharp geometries, the Flow Box is not just a box, but a communication channel between the subconscious and visual representation, transforming unboxing into a deeply personal, experiential experience.
                        </p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="art">
            <span class="section-label" id="lbl-art">08 // ART PORTFOLIO</span>
            <div class="bento-grid">
                <div class="project-card">
                    <img src="art_nature.jpg" alt="Nature" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[PHOTOGRAPHY]</span>
                        <h3 class="p-title" id="art-1-t">Flow in the Forest</h3>
                        <p class="p-desc" id="art-1-d">Landscape composition with running water and atmospheric fog. A study on nature's textures and forest light.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="art_sculpture.jpg" alt="Sculpture" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[MIXED MEDIA / SCULPTURE]</span>
                        <h3 class="p-title" id="art-2-t">Matter and Motion</h3>
                        <p class="p-desc" id="art-2-d">Mixed technique with clay and paper strips. The contrast between the solidity of the base and the lightness of geometric lines.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="art_installation.jpg" alt="Installation" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[INSTALLATION]</span>
                        <h3 class="p-title" id="art-3-t">Symbols and Matter</h3>
                        <p class="p-desc" id="art-3-d">Spatial installation. Clay with metal elements in dialogue with traditional iconography, exploring memory and decay.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="art_digital_1.jpg" alt="Digital Art" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[DIGITAL ART]</span>
                        <h3 class="p-title" id="art-4-t">Urban Fragments</h3>
                        <p class="p-desc" id="art-4-d">Series of three digital compositions. Classical sculpture integrated into a deconstructed urban environment with intense color contrasts.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="art_abstract.jpg" alt="Abstract" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[ABSTRACT / PAINTING]</span>
                        <h3 class="p-title" id="art-5-t">Abstract 1</h3>
                        <p class="p-desc" id="art-5-d">Abstract composition on paper. Focusing on the dynamic movement of black color and the intensity of contrast with the white background.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="art_uncanny.jpg" alt="Staged Photography" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[STAGED PHOTOGRAPHY]</span>
                        <h3 class="p-title" id="art-6-t">Uncanny</h3>
                        <p class="p-desc" id="art-6-d">Photographic record of a human figure in a state of stillness within a classic domestic environment.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="art_abstract_2.jpg" alt="Abstract 2" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[ABSTRACT / INK]</span>
                        <h3 class="p-title" id="art-7-t">Abstract 2</h3>
                        <p class="p-desc" id="art-7-d">An evolution of the gesture series, exploring fluid dynamics and ink dispersion on textured paper.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
                <div class="project-card">
                    <img src="art_abstract_3.jpg" alt="Abstract 3" class="p-img">
                    <div class="p-content">
                        <span class="p-tag mono">[DIGITAL / ABSTRACT]</span>
                        <h3 class="p-title" id="art-8-t">Chrome & Void</h3>
                        <p class="p-desc" id="art-8-d">Digital abstraction focusing on metallic surfaces and the absence of light in virtual spaces.</p>
                        <span class="p-arrow">→</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="projects">
            <span class="section-label" id="lbl-8">08 // FUNDED RESEARCH PROJECTS</span>
            <div class="list-row">
                <div class="list-col-left">EU / CEF</div>
                <div class="list-col-right">
                    <span class="list-title">BYZART - Byzantine Art and Archaeology</span>
                    <span class="list-meta" id="res-1-d">
                        Creation of a thematic channel for the Europeana platform.
                        <a href="https://pro.europeana.eu/project/byzantine-art-and-archaeology" target="_blank" class="pub-link">[VIEW PROJECT]</a>
                    </span>
                </div>
            </div>
        </section>
        <section id="publications">
            <span class="section-label" id="lbl-9">09 // SELECTED PUBLICATIONS</span>
            <div class="list-row">
                <div class="list-col-left">2025</div>
                <div class="list-col-right">
                    <span class="list-title">Reimagining the Erasmus+ Experience through the Metaverse Erasmus Hub</span>
                    <span class="list-meta">Panagiotakopoulos et al. <span class="pub-venue">In NiDS 2025.</span> <a href="https://link.springer.com/chapter/10.1007/978-3-032-10824-1_17" target="_blank" class="pub-link">[Springer]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2025</div>
                <div class="list-col-right">
                    <span class="list-title">APPLICATION OF RENEWABLE ENERGY EFFICIENCY TECHNOLOGIES FOR SUSTAINABLE URBAN DEVELOPMENT</span>
                    <span class="list-meta">Cheirchanteri, Tzortzi, Panagiotakopoulos, Papakitsos. <span class="pub-venue">WJERT Vol 10.0.</span> <a href="https://www.researchgate.net/publication/396270478_APPLICATION_OF_RENEWABLE_ENERGY_EFFICIENCY_TECHNOLOGIES_FOR_SUSTAINABLE_URBAN_DEVELOPMENT_THE_CASE_OF_IOANNINA_GREECE_Original_Article_SJIF_Impact_Factor_7029_Corresponding_Author" target="_blank" class="pub-link">[WJERT]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2025</div>
                <div class="list-col-right">
                    <span class="list-title">Housing Crisis and Digital Worlds: The Potential of the Metaverse in Shaping Practices</span>
                    <span class="list-meta">Panagiotakopoulos, Cheirchanteri. <span class="pub-venue">Housing in Crisis Conference.</span> <a href="https://www.researchgate.net/publication/398587539_HOUSING_CRISIS_AND_DIGITAL_WORLDS_THE_POTENTIAL_OF_THE_METAVERSE_IN_SHAPING_PRACTICES" target="_blank" class="pub-link">[VIEW]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2025</div>
                <div class="list-col-right">
                    <span class="list-title">Participatory Design as a Tool for Inclusive and Ethical Metaverse</span>
                    <span class="list-meta">Panagiotakopoulos et al. <span class="pub-venue">Cumulus Conference 2025.</span> <a href="https://www.researchgate.net/publication/398079015_Participatory_Design_as_a_Tool_for_Inclusive_and_Ethical_Metaverse" target="_blank" class="pub-link">[VIEW]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2025</div>
                <div class="list-col-right">
                    <span class="list-title">The renewable energy sources (RES) efficiency energy technologies: A proposal for the city of Ioannina</span>
                    <span class="list-meta">Cheirchanteri, Tzortzi, Panagiotakopoulos. <span class="pub-venue">Eur. Conf. Ren. Energy Sys.</span> <a href="https://www.researchgate.net/publication/394520201_The_renewable_energy_sources_RES_efficiency_energy_technologies_A_proposal_for_the_city_of_Ioannina_Greece" target="_blank" class="pub-link">[VIEW]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2024</div>
                <div class="list-col-right">
                    <span class="list-title">The Sensory Enrichment and Interactivity of Immersive User Experiences in the Public Sector</span>
                    <span class="list-meta">Deliyannis, Panagiotakopoulos et al. <span class="pub-venue">In Augmented and Virtual Reality in the Metaverse.</span> <a href="https://link.springer.com/chapter/10.1007/978-3-031-57746-8_9?utm_source=researchgate.net&utm_medium=article" target="_blank" class="pub-link">[Springer]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2024</div>
                <div class="list-col-right">
                    <span class="list-title">The Metaverse in Art Education: A Deep Dive into Virtual Collaboration and Creativity</span>
                    <span class="list-meta">Deliyannis, Metzitakos, Panagiotakopoulos. <span class="pub-venue">DCAC 2024.</span> <a href="https://www.researchgate.net/publication/380824491_The_Metaverse_in_Art_Education_A_Deep_Dive_into_Virtual_Collaboration_and_Creativity" target="_blank" class="pub-link">[VIEW]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2024</div>
                <div class="list-col-right">
                    <span class="list-title">Recycling and practices in the interdisciplinary field of Intelligent packaging</span>
                    <span class="list-meta">Mountzouri, Panagiotakopoulos et al. <span class="pub-venue">RETASTE Conference.</span> <a href="https://www.researchgate.net/publication/391482261_Recycling_and_practices_in_the_interdisciplinary_field_of_Intelligent_packaging_Interaction_elements_of_urban_environment_and_metaverse" target="_blank" class="pub-link">[DOI]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2022</div>
                <div class="list-col-right">
                    <span class="list-title">Digital Scent Technology: Toward the Internet of Senses and the Metaverse</span>
                    <span class="list-meta">Panagiotakopoulos et al. <span class="pub-venue">In IT Professional, IEEE, Vol 24.0.</span> <a href="https://www.researchgate.net/publication/360791503_Digital_Scent_Technology_Toward_the_Internet_of_Senses_and_the_Metaverse" target="_blank" class="pub-link">[IEEE]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2022</div>
                <div class="list-col-right">
                    <span class="list-title">Πρακτικά 6ου Επιστημονικού Συνεδρίου: Ευφυής Συσκευασία</span>
                    <span class="list-meta">Panagiotakopoulos (Editor). <span class="pub-venue">ISBN: 978-618-5690-02-1.</span></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2021</div>
                <div class="list-col-right">
                    <span class="list-title">Video Games as Technological Ruins of a Recent Past</span>
                    <span class="list-meta">Metzitakos, Panagiotakopoulos, Christodoulou. <span class="pub-venue">Design|Arts|Culture.</span> <a href="https://ejournals.epublishing.ekt.gr/index.php/DAC/article/view/25904" target="_blank" class="pub-link">[Journal]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2021</div>
                <div class="list-col-right">
                    <span class="list-title">Intelligent ticket and its interaction with transmedia content</span>
                    <span class="list-meta">Panagiotakopoulos et al. <span class="pub-venue">Strategic Innovative Marketing and Tourism.</span> <a href="https://www.researchgate.net/publication/349419331_Intelligent_Ticket_and_its_Interaction_with_Transmedia_Content_in_the_COVID-19_Smart_Tourism_Era" target="_blank" class="pub-link">[Springer]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2021</div>
                <div class="list-col-right">
                    <span class="list-title">AR and NFC Technologies in Smart Tourism Experience</span>
                    <span class="list-meta">Panagiotakopoulos, Christodoulou. <span class="pub-venue">Prospects for Development of Tourism.</span> <a href="https://www.researchgate.net/publication/349861989_AR_and_NFC_Technologies_in_Smart_Tourism_Experience" target="_blank" class="pub-link">[VIEW]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2021</div>
                <div class="list-col-right">
                    <span class="list-title">Augmented Reality and Intelligent Packaging for Smart Tourism</span>
                    <span class="list-meta">Panagiotakopoulos et al. <span class="pub-venue">Augmented Reality in Tourism.</span> <a href="https://www.researchgate.net/publication/346033618_Chapter_4_Augmented_Reality_and_Intelligent_Packaging_for_Smart_Tourism_A_Systematic_Review_and_Analysis" target="_blank" class="pub-link">[Springer]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2020</div>
                <div class="list-col-right">
                    <span class="list-title">Intelligent ticket with augmented reality applications</span>
                    <span class="list-meta">Panagiotakopoulos, Dimitrantzou. <span class="pub-venue">Strategic Innovative Marketing and Tourism.</span> <a href="https://www.researchgate.net/publication/339802046_Intelligent_Ticket_with_Augmented_Reality_Applications_for_Archaeological_Sites" target="_blank" class="pub-link">[Springer]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2020</div>
                <div class="list-col-right">
                    <span class="list-title">Introducing Intelligent Ticket's Dual Role in Degraded Areas</span>
                    <span class="list-meta">Panagiotakopoulos. <span class="pub-venue">Gentrification & Crime.</span> <a href="https://www.researchgate.net/publication/302974322_Transmedia_Perspectives" target="_blank" class="pub-link">[TU Delft]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2020</div>
                <div class="list-col-right">
                    <span class="list-title">Intelligent Urban Waste Management Systems. How Receptive Are We?</span>
                    <span class="list-meta">Konstantinou, Metzitakos, Nomikos, Panagiotakopoulos. <span class="pub-venue">University without Borders.</span> <a href="https://www.researchgate.net/publication/389776194_Konstantinou_P_Metzitakos_R_Stathakis_G_Nomikos_S_and_Panagiotakopoulos_D_2021_Intelligent_Urban_Waste_Management_Systems_How_Receptive_Are_We_Journal_of_Economics_and_Business_Vol_4_No_1_pp_65-80_htt" target="_blank" class="pub-link">[VIEW]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2020</div>
                <div class="list-col-right">
                    <span class="list-title">Gentrification & Crime: New Configurations and Challenges for the City</span>
                    <span class="list-meta">Leoni... Panagiotakopoulos (Chapter). <span class="pub-venue">TU Delft OPEN Publishing.</span> <a href="https://books.bk.tudelft.nl/press/catalog/book/gentrification-and-crime" target="_blank" class="pub-link">[TU Delft]</a></span>
                </div>
            </div>
        </section>
        <section id="activity">
            <span class="section-label" id="lbl-10">10 // ACADEMIC SERVICE & EDITORIAL ACTIVITY</span>
            <div class="list-row">
                <div class="list-col-left">2025 - Pres.</div>
                <div class="list-col-right">
                    <span class="list-title" id="act-1-t">Editorial Board Member</span>
                    <span class="list-meta"><em>Modern Sciences and Sustainable Living (MSSL).</em> <a href="https://sciformat.ca/journals/index.php/mssl" target="_blank" class="pub-link">[Journal Website]</a></span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2026</div>
                <div class="list-col-right">
                    <span class="list-title" id="act-2-t">Peer Reviewer</span>
                    <span class="list-meta" id="act-2-d">Cumulus Athens 2026 Conference. Evaluation and comments on submitted articles.</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2022</div>
                <div class="list-col-right">
                    <span class="list-title" id="act-3-t">Publication Editor</span>
                    <span class="list-meta" id="act-3-d"><em>Proceedings of the 6th Scientific Conference: Intelligent Packaging.</em> ISBN: 978-618-5690-02-1.</span>
                </div>
            </div>
        </section>
        <section id="talks">
            <span class="section-label" id="lbl-11">11 // INVITED TALKS</span>
            <div class="list-row">
                <div class="list-col-left">2024</div>
                <div class="list-col-right">
                    <span class="list-title" id="tlk-1-t">Introduction to the Metaverse Phenomenon</span>
                    <span class="list-meta" id="tlk-1-d">14th Primary of Corfu, Scientific Project Partner of CulturePolis.</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2021</div>
                <div class="list-col-right">
                    <span class="list-title" id="tlk-2-t">Enhancing Experience in Intelligent Packaging</span>
                    <span class="list-meta">Syskevasia Virtual EXPO.</span>
                </div>
            </div>
            <div class="list-row">
                <div class="list-col-left">2016</div>
                <div class="list-col-right">
                    <span class="list-title" id="tlk-3-t">From Reality to Digital (3D Survey)</span>
                    <span class="list-meta">University of Bologna & Minghetti High School.</span>
                </div>
            </div>
        </section>
        <section id="languages">
            <span class="section-label" id="lbl-12">12 // LANGUAGES</span>
            <div style="padding: var(--pad);">
                <p id="txt-lang">Greek (Native), English (Fluent), Italian (Fluent).</p>
            </div>
        </section>
        <section id="contact">
            <span class="section-label" id="lbl-13">13 // CONTACT & LOCATION</span>
            <div class="contact-cta">
                <p style="text-align: center; margin-bottom: 0; font-style: italic; font-size: 1.1rem; color: var(--accent);" id="txt-contact-quote">
                    "Feel free to reach out for research inquiries, collaborations, or student supervision. I am always open to discussing innovative projects and ideas."
                </p>
            </div>
            <div class="contact-grid">
                <div class="contact-details">
                    <ul class="contact-list">
                        <li>
                            <strong id="c-1">Office</strong>
                            Room K16.102, Building K16<br>
                            <span id="c-dept">Dept. of Graphic Design & Visual Communication</span>
                        </li>
                        <li>
                            <strong id="c-2">Address</strong>
                            <span id="c-uni">University of West Attica (Campus 1)</span><br>
                            <span id="c-str">Agiou Spyridonos Str, Egaleo 122 43</span><br>
                            <span id="c-city">Athens, Greece</span>
                        </li>
                        <li>
                            <strong>Email</strong>
                            <a href="mailto:dpanagiotakopoulos@uniwa.gr" style="text-decoration: underline;">dpanagiotakopoulos@uniwa.gr</a>
                        </li>
                        <li>
                            <strong id="c-3">Hours</strong>
                            <span id="c-hrs">Monday - Thursday: 10:00 - 14:00 (By Appointment)</span>
                        </li>
                    </ul>
                </div>
                <div class="map-box">
                    <iframe
                        class="map-frame"
                        width="100%"
                        height="100%"
                        frameborder="0"
                        scrolling="no"
                        marginheight="0"
                        marginwidth="0"
                        src="https://maps.google.com/maps?q=University%20of%20West%20Attica%20Campus%201&t=&z=15&ie=UTF8&iwloc=&output=embed">
                    </iframe>
                </div>
            </div>
        </section>
    </main>
    <footer>
        <p class="mono">© 2026 DIMITRIS PANAGIOTAKOPOULOS. <span id="footer-txt">ACADEMIC PROFILE.</span></p>
    </footer>

    <script>
        // --- TRANSLATION DATA ---
        const translations = {
            en: {
                "txt-h-rank": "PHD CANDIDATE",
                "txt-h-uni": "UNIVERSITY OF WEST ATTICA",
                "txt-h-loc": "ATHENS, GREECE",
                "nav-1": "About", "nav-2": "Dissertation", "nav-3": "Education",
                "nav-4": "Research Themes", "nav-art": "Art Portfolio", "nav-prj": "Funded Projects", 
                "nav-5": "Publications", "nav-6": "Activity", "nav-7": "Contact",
                "lbl-1": "01 // PROFILE",
                "txt-bio-1": "Dimitris Panagiotakopoulos is a Ph.D. Candidate and member of the \"Design, Interior Architecture & Audiovisual Documentation\" research laboratory at the University of West Attica, where he also serves as an Academic Fellow (Teaching Assistant).",
                "txt-bio-2": "His research interests lie within the broader scope of multimedia science, focusing on interaction design and the production process. His doctoral thesis specifically explores <strong>Digital Scent Technology</strong> within the Metaverse, investigating how multisensory interfaces can enhance user experience.",
                "txt-bio-3": "He has worked at the European Commission (DG DIGIT) in Brussels, and previously served as an editor and producer for television advertisements in the private sector in Milan, Italy. His background in Digital Humanities was established through internships at the University of Bologna (Department of History and Culture)—where he participated in the \"BYZART\" European research project—and the Ephorate of Palaeoanthropology and Speleology of the Hellenic Ministry of Culture.",
                "txt-bio-4": "His academic background combines creative arts with advanced technology. He holds an Integrated Master in Audio Visual Arts from the Ionian University and an MSc in \"Intelligent Packaging: New Technologies and Marketing\" from the University of West Attica. Additionally, he attended the Master of Fine Arts (MFA) program at Cardiff Metropolitan University via the Erasmus+ program. He also holds a Certificate of Pedagogical and Teaching Competence, fully qualifying him to teach Art subjects in Primary and Secondary Education.",
                "lbl-2": "02 // PHD DISSERTATION",
                "txt-phd-title": "Olfactory Metaverse Experience Design",
                "txt-phd-quote": "\"But when from a long-distant past nothing subsists... taste and smell alone... bear unfaltering... the vast structure of recollection.\" — Marcel Proust",
                "txt-phd-c1-t": "THE SHIFT", "txt-phd-c1-d": "Transitioning from <strong>Techno-anosmia</strong> to the <strong>3rd Wave</strong> of digital scent, driven by Perceptual Engineering.",
                "txt-phd-c2-t": "THE THEORY", "txt-phd-c2-d": "Defining <strong>Liminal Interaction</strong>: Scent as a connective tissue for <strong>Co-Reality</strong> between physical and digital worlds.",
                "txt-phd-c3-t": "INNOVATION", "txt-phd-c3-d": "Introducing the <strong>OloMET Framework</strong> and the <strong>Spatial Scent GUI</strong> for 3D olfactory diffusion control.",
                "txt-phd-c4-t": "ETHICS", "txt-phd-c4-d": "Proposal for a <strong>Ethical Design Framework</strong> for Neurorights, covering the legal gap in mental privacy.",
                "lbl-3": "03 // EDUCATION",
                "edu-1-t": "Ph.D. Candidate (8 EQF)", "edu-1-d": "Dept. of Graphic Design & Visual Communication, University of West Attica.<br><strong>Thesis:</strong> \"Digital Scent Technology in Metaverse Environments\"",
                "edu-2-t": "Specialized Programme of Studies for Certification of Pedagogical and Teaching Competence", "edu-2-d": "Ionian University. Teaching Practicum: 7th Gymnasium of Corfu, Greece.",
                "edu-3-t": "MSc in Intelligent Packaging: New Technologies & Marketing", "edu-3-d": "University of West Attica (90 ECTS, 7 EQF).",
                "edu-4-t": "Integrated Master in Audio Visual Arts", "edu-4-d": "Ionian University (300 ECTS, 7 EQF).",
                "edu-5-t": "Erasmus+ (MFA Module)", "edu-5-d": "Cardiff Metropolitan University.",
                "lbl-4": "04 // AWARDS & SCHOLARSHIPS",
                "aw-1-t": "Most Popular Article Award", "aw-1-d": "Awarded by <em>IEEE IT Professional</em> for the article \"Digital Scent Technology Toward the Internet of Senses and the Metaverse\".",
                "aw-2-t": "Doctorate Scholarship", "aw-2-d": "Special Account for Research Funds (ELKE), University of West Attica.",
                "aw-3-t": "Erasmus+ Scholarship for Traineeship", "aw-3-d": "University of Bologna, Italy (Digital Humanities).",
                "aw-4-t": "Erasmus+ Scholarship for Studies", "aw-4-d": "Cardiff Metropolitan University, UK (Master of Fine Arts).",
                "lbl-5": "05 // TEACHING EXPERIENCE",
                "tea-1-t": "Teaching Assistant (Academic Fellow)", "tea-1-d": "University of West Attica. Courses: 1) <em>Multimedia Graphic Design</em>, 2) <em>Digital Interactive Multimedia Applications</em>",
                "tea-2-t": "Mentoring & Thesis Supervision", "tea-2-d": "Master thesis Co-Supervisions & Mentoring programme, University of West Attica.",
                "lbl-6": "06 // INTERNATIONAL MOBILITY",
                "mob-1-t": "Erasmus+ ICM – Visiting PhD Researcher", "mob-1-d": "Technical University of Moldova (UTM), Chișinău.",
                "lbl-7": "07 // RESEARCH THEMES & CASE STUDIES",
                "pj-1-t": "Sacred Futurism", "pj-1-d": "The project presents a series of artworks and their analysis under the theme of Sacred Futurism. It explores the contrast between the sacred and technology by depicting robots in the roles of traditional holy figures, rendered in a Byzantine style. Set against post-apocalyptic landscapes, the works address ecological destruction while suggesting that, in a dystopian future, robots may rebuild society based on ethical values and the protection of life. The analysis examines the relationship between religion, the metaverse, robotics, and artificial intelligence, discussing concepts such as transhumanism and \"Robot Theology.\"",
                "pj-2-t": "Digital Scent Technology & IoS", "pj-2-d": "Exploring multisensory interface technologies for HCI, focusing on digital scent. Reviews current electrical interfaces, chemical odor delivery, and the commercial potential of the Internet of Senses (IoS) and 6G infrastructure.",
                "pj-3-t": "Spatial User Interfaces", "pj-3-d": "Developing 3D controls for olfactory diffusion in immersive environments. The project addresses the lack of visual tools for designing scent in the Metaverse.",
                "pj-4-t": "METAVERSE in Public Sector", "pj-4-d": "Examining the application of Virtual Reality in the public sector. Explores sensory enhancement (haptic, auditory, olfactory) to create immersive experiences.",
                "pj-5-t": "Metaverse Erasmus Hub", "pj-5-d": "A proposal to the European Commission for integrating metaverse technologies into Erasmus+. Enhances physical mobility via AI avatars.",
                "pj-6-t": "Metaverse in Education", "pj-6-d": "Case study with 20 students using Spatial. Findings indicate increased creativity (50%) and interest in technology integration (70%).",
                "pj-7-t": "INTELLIGENT Packaging", "pj-7-d": "Exploring smart packaging as a key trend in tourism, blending physical and digital worlds via IoT, 5G, RFID, and NFC.",
                "pj-8-t": "Prinzhorn Collection & VR", "pj-8-d": "Study on psychiatric artworks (Heidelberg) to explore emotion elicitation and simulate psychosis in VR environments.",
                "pj-9-t": "ETHICAL METAVERSE", "pj-9-d": "Participatory Design (PD) as an ethical necessity for building an inclusive Metaverse. Rooted in the philosophy of Ubuntu.",
                "pj-10-t": "KAFKAESQUE LABYRINTH", "pj-10-d": "Through an innovative educational approach to Kafka's work, hypertext fiction practices are employed. In search of the thread of interpretation, thoughts, experiences, and reflections are transformed into a creative artistic response. The interpretative process emerges as a field where art and technology intersect. <br><br> @ Panagiotakopoulos / Hyper-Kafka Memory Rooms",
                "pj-11-t": "FLOQ BOX", "pj-11-d": "The Flow Box is inspired by the concept of \"fluidity\" in the modern world and explores human emotions. The device uses Affective Computing technologies to recognize the user's emotions, which it then metabolizes and represents through holographic simulation. With industrial materials (PVC, metal) and sharp geometries, the Flow Box is not just a box, but a communication channel between the subconscious and visual representation, transforming unboxing into a deeply personal, experiential experience.",
                "lbl-art": "08 // ART PORTFOLIO",
                "art-1-t": "Flow in the Forest", "art-1-d": "Landscape composition with running water and atmospheric fog. A study on nature's textures and forest light.",
                "art-2-t": "Matter and Motion", "art-2-d": "Mixed technique with clay and paper strips. The contrast between the solidity of the base and the lightness of geometric lines.",
                "art-3-t": "Symbols and Matter", "art-3-d": "Spatial installation. Clay with metal elements in dialogue with traditional iconography, exploring memory and decay.",
                "art-4-t": "Urban Fragments", "art-4-d": "Series of three digital compositions. Classical sculpture integrated into a deconstructed urban environment with intense color contrasts.",
                "art-5-t": "Abstract 1", "art-5-d": "Abstract composition on paper. Focusing on the dynamic movement of black color and the intensity of contrast with the white background.",
                "art-6-t": "Uncanny", "art-6-d": "Photographic record of a human figure in a state of stillness within a classic domestic environment.",
                "art-7-t": "Abstract 2", "art-7-d": "An evolution of the gesture series, exploring fluid dynamics and ink dispersion on textured paper.",
                "art-8-t": "Chrome & Void", "art-8-d": "Digital abstraction focusing on metallic surfaces and the absence of light in virtual spaces.",
                "lbl-8": "08 // FUNDED RESEARCH PROJECTS", "res-1-d": "Creation of a thematic channel for the Europeana platform. <a href=\"https://pro.europeana.eu/project/byzantine-art-and-archaeology\" target=\"_blank\" class=\"pub-link\">[VIEW PROJECT]</a>",
                "lbl-9": "09 // SELECTED PUBLICATIONS",
                "lbl-10": "10 // ACADEMIC SERVICE & EDITORIAL ACTIVITY",
                "act-1-t": "Editorial Board Member",
                "act-2-t": "Peer Reviewer", "act-2-d": "Cumulus Athens 2026 Conference. Evaluation and comments on submitted articles.",
                "act-3-t": "Publication Editor", "act-3-d": "<em>Proceedings of the 6th Scientific Conference: Intelligent Packaging.</em> ISBN: 978-618-5690-02-1.",
                "lbl-11": "11 // INVITED TALKS",
                "tlk-1-t": "Introduction to the Metaverse Phenomenon", "tlk-1-d": "14th Primary of Corfu, Scientific Project Partner of CulturePolis.",
                "tlk-2-t": "Enhancing Experience in Intelligent Packaging",
                "tlk-3-t": "From Reality to Digital (3D Survey)",
                "lbl-12": "12 // LANGUAGES", "txt-lang": "Greek (Native), English (Fluent), Italian (Fluent).",
                "lbl-13": "13 // CONTACT & LOCATION",
                "txt-contact-quote": "\"Feel free to reach out for research inquiries, collaborations, or student supervision. I am always open to discussing innovative projects and ideas.\"",
                "c-1": "Office", "c-dept": "Dept. of Graphic Design & Visual Communication",
                "c-2": "Address", "c-uni": "University of West Attica (Campus 1)", "c-str": "Agiou Spyridonos Str, Egaleo 122 43", "c-city": "Athens, Greece",
                "c-3": "Hours", "c-hrs": "Monday - Thursday: 10:00 - 14:00 (By Appointment)",
                "footer-txt": "ACADEMIC PROFILE."
            },
            gr: {
                "txt-h-rank": "ΥΠΟΨΗΦΙΟΣ ΔΙΔΑΚΤΩΡ",
                "txt-h-uni": "ΠΑΝΕΠΙΣΤΗΜΙΟ ΔΥΤΙΚΗΣ ΑΤΤΙΚΗΣ",
                "txt-h-loc": "ΑΘΗΝΑ, ΕΛΛΑΔΑ",
                "nav-1": "Προφίλ", "nav-2": "Διατριβή", "nav-3": "Εκπαίδευση",
                "nav-4": "Έρευνα", "nav-art": "Καλλιτεχνικό Έργο", "nav-prj": "Χρηματοδοτούμενα Έργα",
                "nav-5": "Δημοσιεύσεις", "nav-6": "Δραστηριότητα", "nav-7": "Επικοινωνία",
                "lbl-1": "01 // ΠΡΟΦΙΛ",
                "txt-bio-1": "Ο Δημήτρης Παναγιωτακόπουλος είναι Υποψήφιος Διδάκτωρ και μέλος του ερευνητικού εργαστηρίου «Σχεδιασμού, Εσωτερικής Αρχιτεκτονικής & Οπτικοακουστικής Τεκμηρίωσης» του Πανεπιστημίου Δυτικής Αττικής, όπου υπηρετεί και ως Ακαδημαϊκός Υπότροφος.",
                "txt-bio-2": "Τα ερευνητικά του ενδιαφέροντα εντάσσονται στο ευρύτερο πεδίο της επιστήμης των πολυμέσων, με έμφαση στον σχεδιασμό αλληλεπίδρασης. Η διδακτορική του διατριβή εξετάζει συγκεκριμένα την <strong>Τεχνολογία Ψηφιακής Οσμής</strong> (Digital Scent) στο Metaverse, διερευνώντας πώς οι πολυαισθητηριακές διεπαφές μπορούν να ενισχύσουν την εμπειρία του χρήστη.",
                "txt-bio-3": "Έχει εργαστεί στην Ευρωπαϊκή Επιτροπή (DG DIGIT) στις Βρυξέλλες, ενώ προηγουμένως εργάστηκε ως μοντέρ και παραγωγός τηλεοπτικών διαφημίσεων στον ιδιωτικό τομέα στο Μιλάνο. Το υπόβαθρό του στις Ψηφιακές Ανθρωπιστικές Επιστήμες εδραιώθηκε μέσω πρακτικής άσκησης στο Πανεπιστήμιο της Μπολόνια (Τμήμα Ιστορίας και Πολιτισμού) —όπου συμμετείχε στο ευρωπαϊκό ερευνητικό έργο «BYZART»— και στην Εφορεία Παλαιοανθρωπολογίας και Σπηλαιολογίας του Υπουργείου Πολιτισμού.",
                "txt-bio-4": "Το ακαδημαϊκό του υπόβαθρο συνδυάζει τις δημιουργικές τέχνες με την προηγμένη τεχνολογία. Κατέχει Integrated Master στις Οπτικοακουστικές Τέχνες από το Ιόνιο Πανεπιστήμιο και MSc στην «Ευφυή Συσκευασία: Νέες Τεχνολογίες και Μάρκετινγκ» από το Πανεπιστήμιο Δυτικής Αττικής. Επιπλέον, παρακολούθησε το πρόγραμμα Master of Fine Arts (MFA) στο Cardiff Metropolitan University μέσω του προγράμματος Erasmus+. Διαθέτει επίσης Πιστοποιητικό Παιδαγωγικής και Διδακτικής Επάρκειας για διδασκαλία μαθημάτων Καλλιτεχνικών στην Πρωτοβάθμια και Δευτεροβάθμια Εκπαίδευση.",
                "lbl-2": "02 // ΔΙΔΑΚΤΟΡΙΚΗ ΔΙΑΤΡΙΒΗ",
                "txt-phd-title": "Σχεδιασμός Οσφρητικής Εμπειρίας στο Metaverse",
                "txt-phd-quote": "«Αλλά όταν από ένα μακρινό παρελθόν τίποτα δεν επιβιώνει... η γεύση και η οσμή παραμένουν... για να στηρίξουν το τεράστιο οικοδόμημα της ανάμνησης.» — Μαρσέλ Προυστ",
                "txt-phd-c1-t": "Η ΜΕΤΑΒΑΣΗ", "txt-phd-c1-d": "Μετάβαση από την <strong>Τεχνο-ανοσμία</strong> στο <strong>3ο Κύμα</strong> της ψηφιακής οσμής, οδηγούμενη από την Αντιληπτική Μηχανική.",
                "txt-phd-c2-t": "Η ΘΕΩΡΙΑ", "txt-phd-c2-d": "Ορισμός της <strong>Οριακής Αλληλεπίδρασης</strong>: Η οσμή ως συνδετικός ιστός για τη <strong>Συν-Πραγματικότητα</strong> μεταξύ φυσικού και ψηφιακού κόσμου.",
                "txt-phd-c3-t": "ΚΑΙΝΟΤΟΜΙΑ", "txt-phd-c3-d": "Εισαγωγή του πλαισίου <strong>OloMET</strong> και του <strong>Spatial Scent GUI</strong> για τον έλεγχο της οσφρητικής διάχυσης σε 3D χώρο.",
                "txt-phd-c4-t": "ΗΘΙΚΗ", "txt-phd-c4-d": "Πρόταση ενός <strong>Πλαισίου Ηθικού Σχεδιασμού</strong> για τα Νευροδικαιώματα, καλύπτοντας το νομικό κενό στην πνευματική ιδιωτικότητα.",
                "lbl-3": "03 // ΕΚΠΑΙΔΕΥΣΗ",
                "edu-1-t": "Υποψήφιος Διδάκτωρ (8 EQF)", "edu-1-d": "Τμήμα Γραφιστικής & Οπτικής Επικοινωνίας, Πανεπιστήμιο Δυτικής Αττικής.<br><strong>Διατριβή:</strong> «Τεχνολογία Ψηφιακής Οσμής σε Περιβάλλοντα Metaverse»",
                "edu-2-t": " Ειδικό Πρόγραμμα Σπουδών Πιστοποίησης Παιδαγωγικής και Διδακτικής Επάρκειας", "edu-2-d": "Ιόνιο Πανεπιστήμιο. Πρακτική Άσκηση στο 7ο Γυμνάσιο Κέρκυρας.",
                "edu-3-t": "MSc στην Ευφυή Συσκευασία: Νέες Τεχνολογίες & Μάρκετινγκ", "edu-3-d": "Πανεπιστήμιο Δυτικής Αττικής (90 ECTS, 7 EQF).",
                "edu-4-t": "Ενιαίος και Αδιάσπαστος Τίτλος Σπουδών Μεταπτυχιακού Επιπέδου (Integrated Master) στις Οπτικοακουστικές Τέχνες", "edu-4-d": "Ιόνιο Πανεπιστήμιο (300 ECTS, 7 EQF).",
                "edu-5-t": "Erasmus+ (Master of Fine Arts)", "edu-5-d": "Cardiff Metropolitan University.",
                "lbl-4": "04 // ΒΡΑΒΕΙΑ & ΥΠΟΤΡΟΦΙΕΣ",
                "aw-1-t": "Βραβείο Δημοφιλέστερου Άρθρου", "aw-1-d": "Απονεμήθηκε από το <em>IEEE IT Professional</em> για το άρθρο «Digital Scent Technology Toward the Internet of Senses and the Metaverse».",
                "aw-2-t": "Υποτροφία Διδακτορικών Σπουδών", "aw-2-d": "Ειδικός Λογαριασμός Κονδυλίων Έρευνας (ΕΛΚΕ), ΠΑΔΑ.",
                "aw-3-t": "Υποτροφία Erasmus+ για Πρακτική Άσκηση", "aw-3-d": "Πανεπιστήμιο της Μπολόνια, Ιταλία (Ψηφιακές Ανθρωπιστικές Επιστήμες).",
                "aw-4-t": "Υποτροφία Erasmus+ για Σπουδές", "aw-4-d": "Cardiff Metropolitan University, ΗΒ (Master of Fine Arts).",
                "lbl-5": "05 // ΔΙΔΑΚΤΙΚΗ ΕΜΠΕΙΡΙΑ",
                "tea-1-t": "Ακαδημαϊκός Υπότροφος (Βοηθός Διδασκαλίας)", "tea-1-d": "Πανεπιστήμιο Δυτικής Αττικής. Μαθήματα: 1) <em>Σχεδιασμός Πολυμέσων</em>, 2) <em>Ψηφιακές Διαδραστικές Εφαρμογές Πολυμέσων</em>",
                "tea-2-t": "Mentoring & Επίβλεψη Πτυχιακών", "tea-2-d": "Συνεπιβλέψεις μεταπτυχιακών εργασιών & πρόγραμμα Mentoring, ΠΑΔΑ.",
                "lbl-6": "06 // ΔΙΕΘΝΗΣ ΚΙΝΗΤΙΚΟΤΗΤΑ",
                "mob-1-t": "Erasmus+ ICM – Επισκέπτης Ερευνητής PhD", "mob-1-d": "Τεχνικό Πανεπιστήμιο της Μολδαβίας (UTM), Κισινάου.",
                "lbl-7": "07 // ΕΡΕΥΝΗΤΙΚΑ ΘΕΜΑΤΑ & CASE STUDIES",
                "pj-1-t": "Sacred Futurism", "pj-1-d": "Το έργο παρουσιάζει μια σειρά καλλιτεχνικών έργων και την ανάλυσή τους με θέμα τον Ιερό Φουτουρισμό. Εξερευνά την αντίθεση μεταξύ του ιερού και της τεχνολογίας, απεικονίζοντας ρομπότ σε ρόλους παραδοσιακών αγίων μορφών, σε βυζαντινό στυλ. Τοποθετημένα σε μετα-αποκαλυπτικά τοπία, τα έργα πραγματεύονται την οικολογική καταστροφή, προτείνοντας ότι σε ένα δυστοπικό μέλλον, τα ρομπότ μπορεί να ανοικοδομήσουν την κοινωνία βασισμένα σε ηθικές αξίες. Η ανάλυση εξετάζει τη σχέση θρησκείας, metaverse, ρομποτικής και AI, συζητώντας έννοιες όπως ο μετανθρωπισμός και η «Θεολογία των Ρομπότ».",
                "pj-2-t": "Digital Scent Technology & IoS", "pj-2-d": "Εξερεύνηση πολυαισθητηριακών διεπαφών για HCI, με έμφαση στην ψηφιακή οσμή. Ανασκόπηση των τρεχουσών ηλεκτρικών διεπαφών, της χημικής παροχής οσμών και των εμπορικών δυνατοτήτων του Internet of Senses (IoS) και των υποδομών 6G.",
                "pj-3-t": "Spatial User Interfaces", "pj-3-d": "Ανάπτυξη τρισδιάστατων χειριστηρίων (3D controls) για τη διάχυση οσμών σε εμβυθιστικά περιβάλλοντα. Το έργο αντιμετωπίζει την έλλειψη οπτικών εργαλείων για τον σχεδιασμό οσμής στο Metaverse.",
                "pj-4-t": "METAVERSE στον Δημόσιο Τομέα", "pj-4-d": "Εξέταση της εφαρμογής της Εικονικής Πραγματικότητας στον δημόσιο τομέα. Εξερευνά την αισθητηριακή ενίσχυση (απτική, ακουστική, οσφρητική) για τη δημιουργία εμβυθιστικών εμπειριών.",
                "pj-5-t": "Metaverse Erasmus Hub", "pj-5-d": "Πρόταση προς την Ευρωπαϊκή Επιτροπή για την ενσωμάτωση τεχνολογιών metaverse στο πρόγραμμα Erasmus+. Ενίσχυση της φυσικής κινητικότητας μέσω AI avatars.",
                "pj-6-t": "Metaverse στην Εκπαίδευση", "pj-6-d": "Μελέτη περίπτωσης με 20 φοιτητές χρησιμοποιώντας το Spatial. Τα ευρήματα δείχνουν αυξημένη δημιουργικότητα (50%) και ενδιαφέρον για την ενσωμάτωση τεχνολογίας (70%).",
                "pj-7-t": "ΕΥΦΥΗΣ Συσκευασία", "pj-7-d": "Εξερεύνηση της έξυπνης συσκευασίας ως βασική τάση στον τουρισμό, συνδυάζοντας τον φυσικό και τον ψηφιακό κόσμο μέσω IoT, 5G, RFID και NFC.",
                "pj-8-t": "Συλλογή Prinzhorn & VR", "pj-8-d": "Μελέτη σε ψυχιατρικά έργα τέχνης (Χαϊδελβέργη) για την εξερεύνηση της πρόκλησης συναισθημάτων και την προσομοίωση ψύχωσης σε περιβάλλοντα VR.",
                "pj-9-t": "ΗΘΙΚΟ METAVERSE", "pj-9-d": "Ο Συμμετοχικός Σχεδιασμός (PD) ως ηθική αναγκαιότητα για την οικοδόμηση ενός συμπεριληπτικού Metaverse. Ριζωμένο στη φιλοσοφία του Ubuntu.",
                "pj-10-t": "ΚΑΦΚΙΚΟΣ ΛΑΒΥΡΙΝΘΟΣ", "pj-10-d": "Μέσα από μια καινοτόμο εκπαιδευτική προσέγγιση στο έργο του Κάφκα, επιστρατεύονται πρακτικές υπερκειμενικής μυθοπλασίας. Αναζητώντας το μίτο της ερμηνείας, σκέψεις, βιώματα και στοχασμοί μετουσιώνονται σε μια δημιουργική καλλιτεχνική απόκριση. Η ερμηνευτική διαδικασία αναδύεται ως ένα πεδίο όπου η τέχνη συναντά την τεχνολογία. <br><br> @ Panagiotakopoulos / Hyper-Kafka Memory Rooms",
                "pj-11-t": "FLOQ BOX", "pj-11-d": "Το Flow Box αποτελεί είναι εμπνευσμένο από την έννοια της «ρευστότητας» του σύγχρονου κόσμου και εξερευνά την εξερεύνηση των ανθρώπινων συναισθημάτων. Η συσκευή χρησιμοποιεί τεχνολογίες Affective Computing για την αναγνώριση των συναισθημάτων του χρήστη, τα οποία στη συνέχεια μεταβολίζει και αναπαριστά μέσω ολογραμματικής προσομοίωσης. Βιομηχανικά υλικά (PVC, μέταλλο) και αιχμηρές γεωμετρίες, το Flow Box δεν είναι απλώς ένα κουτί, αλλά ένας δίαυλος επικοινωνίας μεταξύ του υποσυνείδητου και της οπτικής αναπαράστασης, μετατρέποντας την αποσυσκευασία (unboxing) σε μια βαθιά προσωπική, βιωματική εμπειρία.",
                "lbl-art": "08 // ΚΑΛΛΙΤΕΧΝΙΚΟ ΧΑΡΤΟΦΥΛΑΚΙΟ",
                "art-1-t": "Ροή στο Δάσος", "art-1-d": "Σύνθεση τοπίου με τρεχούμενο νερό και ατμοσφαιρική ομίχλη. Μια μελέτη πάνω στις υφές της φύσης και το φως του δάσους.",
                "art-2-t": "Ύλη και Κίνηση", "art-2-d": "Μικτή τεχνική με πηλό και λωρίδες χαρτιού. Η αντίθεση ανάμεσα στη στιβαρότητα της βάσης και την ελαφρότητα των γεωμετρικών γραμμών.",
                "art-3-t": "Σύμβολα και Ύλη", "art-3-d": "Εγκατάσταση στο χώρο. Πηλός με μεταλλικά στοιχεία σε διάλογο με την παραδοσιακή εικονογραφία, εξερευνώντας τη μνήμη και τη φθορά.",
                "art-4-t": "Αστικά Θραύσματα", "art-4-d": "Σειρά τριών ψηφιακών συνθέσεων. Η κλασική γλυπτική εντάσσεται σε ένα αποδομημένο αστικό περιβάλλον με έντονες χρωματικές αντιθέσεις.",
                "art-5-t": "Abstract 1", "art-5-d": "Αφηρημένη σύνθεση σε χαρτί. Εστίαση στη δυναμική κίνηση του μαύρου χρώματος και στην ένταση της αντίθεσης με το λευκό φόντο.",
                "art-6-t": "Uncanny", "art-6-d": "Φωτογραφική καταγραφή μιας ανθρώπινης μορφής σε κατάσταση ακινησίας μέσα σε ένα κλασικό οικιακό περιβάλλον.",
                "art-7-t": "Abstract 2", "art-7-d": "Μια εξέλιξη της σειράς gestures, εξερευνώντας τη δυναμική των ρευστών και τη διάχυση μελάνης σε ανάγλυφο χαρτί.",
                "art-8-t": "Chrome & Void", "art-8-d": "Ψηφιακή αφαίρεση με επίκεντρο τις μεταλλικές επιφάνειες και την απουσία φωτός σε εικονικούς χώρους.",
                "lbl-8": "08 // ΧΡΗΜΑΤΟΔΟΤΟΥΜΕΝΑ ΕΡΕΥΝΗΤΙΚΑ ΕΡΓΑ", "res-1-d": "Δημιουργία θεματικού καναλιού για την πλατφόρμα Europeana. <a href=\"https://pro.europeana.eu/project/byzantine-art-and-archaeology\" target=\"_blank\" class=\"pub-link\">[VIEW PROJECT]</a>",
                "lbl-9": "09 // ΕΠΙΛΕΓΜΕΝΕΣ ΔΗΜΟΣΙΕΥΣΕΙΣ",
                "lbl-10": "10 // ΑΚΑΔΗΜΑΪΚΟ ΕΡΓΟ & ΣΥΝΤΑΚΤΙΚΗ ΔΡΑΣΤΗΡΙΟΤΗΤΑ",
                "act-1-t": "Μέλος Συντακτικής Επιτροπής",
                "act-2-t": "Peer Reviewer (Κριτής)", "act-2-d": "Συνέδριο Cumulus Athens 2026. Αξιολόγηση και σχολιασμός υποβληθέντων άρθρων.",
                "act-3-t": "Επιμελητής Έκδοσης", "act-3-d": "<em>Πρακτικά 6ου Επιστημονικού Συνεδρίου: Ευφυής Συσκευασία.</em> ISBN: 978-618-5690-02-1.",
                "lbl-11": "11 // ΟΜΙΛΙΕΣ",
                "tlk-1-t": "Εισαγωγή στο Φαινόμενο του Metaverse", "tlk-1-d": "14ο Δημοτικό Σχολείο Κέρκυρας, Επιστημονικός Συνεργάτης CulturePolis.",
                "tlk-2-t": "Ενίσχυση της Εμπειρίας στην Ευφυή Συσκευασία",
                "tlk-3-t": "Από την Πραγματικότητα στο Ψηφιακό (3D Survey)",
                "lbl-12": "12 // ΓΛΩΣΣΕΣ", "txt-lang": "Ελληνικά (Μητρική), Αγγλικά (Άριστα), Ιταλικά (Άριστα).",
                "lbl-13": "13 // ΕΠΙΚΟΙΝΩΝΙΑ",
                "txt-contact-quote": "«Μη διστάσετε να επικοινωνήσετε για ερευνητικά ερωτήματα, συνεργασίες ή επίβλεψη φοιτητών. Είμαι πάντα ανοιχτός σε συζητήσεις για καινοτόμα έργα και ιδέες.»",
                "c-1": "Γραφείο", "c-dept": "Τμήμα Γραφιστικής & Οπτικής Επικοινωνίας",
                "c-2": "Διεύθυνση", "c-uni": "Πανεπιστήμιο Δυτικής Αττικής (Άλσος Αιγάλεω)", "c-str": "Αγίου Σπυρίδωνος, Αιγάλεω 122 43", "c-city": "Αθήνα, Ελλάδα",
                "c-3": "Ώρες", "c-hrs": "Δευτέρα - Πέμπτη: 10:00 - 14:00 (Κατόπιν Ραντεβού)",
                "footer-txt": "ΑΚΑΔΗΜΑΪΚΟ ΠΡΟΦΙΛ."
            }
        };

        // --- THEME LOGIC ---
        const themeBtn = document.getElementById('theme-btn');
        function updateTheme(theme) {
            if (theme === 'dark') document.body.setAttribute('data-theme', 'dark');
            else document.body.removeAttribute('data-theme');
        }
        themeBtn.addEventListener('click', () => {
            const current = document.body.getAttribute('data-theme');
            const newTheme = current === 'dark' ? 'light' : 'dark';
            updateTheme(newTheme);
            localStorage.setItem('theme', newTheme);
        });
        const savedTheme = localStorage.getItem('theme');
        if (savedTheme) updateTheme(savedTheme);

        // --- LANGUAGE LOGIC ---
        const langBtn = document.getElementById('lang-btn');
        let currentLang = localStorage.getItem('lang') || 'en';

        function setLanguage(lang) {
            const data = translations[lang];
            for (const key in data) {
                const element = document.getElementById(key);
                if (element) {
                    element.innerHTML = data[key];
                }
            }
            langBtn.innerText = lang === 'en' ? 'GR' : 'EN';
            document.documentElement.lang = lang;
        }

        langBtn.addEventListener('click', () => {
            currentLang = currentLang === 'en' ? 'gr' : 'en';
            setLanguage(currentLang);
            localStorage.setItem('lang', currentLang);
        });

        // Initialize Language
        setLanguage(currentLang);
    </script>
</body>
</html>
