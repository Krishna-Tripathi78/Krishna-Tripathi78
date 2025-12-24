<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Krishna Tripathi - GitHub Profile Preview</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0d1117;
            color: #c9d1d9;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Animated Header */
        .header {
            background: linear-gradient(135deg, #00ff00 0%, #00aa00 50%, #005500 100%);
            padding: 60px 20px;
            text-align: center;
            border-radius: 10px;
            margin-bottom: 30px;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            animation: wave 3s linear infinite;
        }

        @keyframes wave {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .header h1 {
            font-size: 48px;
            color: white;
            position: relative;
            z-index: 1;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .header p {
            font-size: 18px;
            color: #f0f0f0;
            margin-top: 10px;
            position: relative;
            z-index: 1;
        }

        /* Typing Animation */
        .typing-container {
            text-align: center;
            margin: 30px 0;
            min-height: 60px;
        }

        .typing-text {
            font-size: 24px;
            color: #00ff00;
            font-family: 'Courier New', monospace;
            border-right: 3px solid #00ff00;
            padding-right: 5px;
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 50% { border-color: #00ff00; }
            51%, 100% { border-color: transparent; }
        }

        /* Section Styles */
        .section {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 10px;
            padding: 30px;
            margin-bottom: 30px;
        }

        .section-title {
            color: #00ff00;
            font-size: 28px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section-title::before {
            content: '🟢';
            font-size: 20px;
        }

        /* Terminal Style */
        .terminal {
            background: #000;
            border: 2px solid #00ff00;
            border-radius: 8px;
            padding: 20px;
            font-family: 'Courier New', monospace;
            color: #00ff00;
            margin: 20px 0;
        }

        .terminal-line {
            margin: 5px 0;
        }

        .terminal-prompt {
            color: #00ff00;
            font-weight: bold;
        }

        /* Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }

        .stat-card {
            background: linear-gradient(135deg, #1a1b27 0%, #2d2f3e 100%);
            border: 2px solid #00ff00;
            border-radius: 10px;
            padding: 30px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 255, 0, 0.3);
        }

        .stat-number {
            font-size: 48px;
            color: #00ff00;
            font-weight: bold;
            margin: 10px 0;
        }

        .stat-label {
            color: #8b949e;
            font-size: 16px;
        }

        /* Tech Stack */
        .tech-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin: 20px 0;
        }

        .tech-badge {
            background: #1a1b27;
            border: 2px solid #00ff00;
            border-radius: 20px;
            padding: 10px 20px;
            color: #00ff00;
            font-weight: bold;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-badge:hover {
            background: #00ff00;
            color: #000;
            transform: scale(1.1);
        }

        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }

        .project-card {
            background: #1a1b27;
            border: 2px solid #30363d;
            border-radius: 10px;
            padding: 25px;
            transition: all 0.3s ease;
        }

        .project-card:hover {
            border-color: #00ff00;
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 255, 0, 0.2);
        }

        .project-title {
            color: #00ff00;
            font-size: 22px;
            margin-bottom: 10px;
        }

        .project-desc {
            color: #8b949e;
            margin-bottom: 15px;
        }

        .project-tech {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .tech-tag {
            background: #00ff00;
            color: #000;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 12px;
            font-weight: bold;
        }

        /* Contribution Graph */
        .contribution-graph {
            margin: 20px 0;
        }

        .graph-container {
            display: grid;
            grid-template-columns: repeat(53, 1fr);
            gap: 3px;
            margin-top: 20px;
        }

        .graph-cell {
            aspect-ratio: 1;
            border-radius: 2px;
            background: #161b22;
            transition: all 0.3s ease;
        }

        .graph-cell.active-1 { background: #003300; }
        .graph-cell.active-2 { background: #006600; }
        .graph-cell.active-3 { background: #009900; }
        .graph-cell.active-4 { background: #00ff00; }

        /* Achievements */
        .achievements {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
        }

        .achievement-card {
            background: linear-gradient(135deg, #1a1b27 0%, #2d2f3e 100%);
            border-left: 4px solid #00ff00;
            padding: 20px;
            border-radius: 8px;
        }

        .achievement-icon {
            font-size: 32px;
            margin-bottom: 10px;
        }

        .achievement-title {
            color: #00ff00;
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .achievement-desc {
            color: #8b949e;
            font-size: 14px;
        }

        /* Contact Links */
        .contact-links {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            justify-content: center;
            margin: 30px 0;
        }

        .contact-btn {
            background: #1a1b27;
            border: 2px solid #00ff00;
            color: #00ff00;
            padding: 12px 30px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .contact-btn:hover {
            background: #00ff00;
            color: #000;
            transform: scale(1.05);
        }

        /* Profile Views Counter */
        .profile-views {
            text-align: center;
            margin: 20px 0;
            color: #00ff00;
            font-size: 14px;
        }

        @media (max-width: 768px) {
            .header h1 { font-size: 32px; }
            .typing-text { font-size: 18px; }
            .section-title { font-size: 22px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Animated Header -->
        <div class="header">
            <h1>👋 Krishna Tripathi</h1>
            <p>Cybersecurity Engineer | DevOps Enthusiast | Open Source Builder</p>
        </div>

        <div class="profile-views">👁️ Profile Views: 1,247</div>

        <!-- Typing Animation -->
        <div class="typing-container">
            <div class="typing-text" id="typingText"></div>
        </div>

        <!-- Terminal Identity -->
        <div class="section">
            <h2 class="section-title">TERMINAL IDENTITY</h2>
            <div class="terminal">
                <div class="terminal-line"><span class="terminal-prompt">krishna@github:~$</span> whoami</div>
                <div class="terminal-line">-----------------------------------</div>
                <div class="terminal-line">Name        : Krishna Tripathi</div>
                <div class="terminal-line">Location    : Kanpur, India</div>
                <div class="terminal-line">Education   : B.Tech CS (Cyber Security)</div>
                <div class="terminal-line">University  : AKTU</div>
                <div class="terminal-line">Community   : FOSS United Kanpur (Core)</div>
                <div class="terminal-line">Focus       : Security • DevOps • Cloud</div>
                <div class="terminal-line">Status      : Always Learning 🚀</div>
                <div class="terminal-line">-----------------------------------</div>
            </div>
        </div>

        <!-- GitHub Stats -->
        <div class="section">
            <h2 class="section-title">GITHUB STATS</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-label">Total Contributions</div>
                    <div class="stat-number">155</div>
                    <div class="stat-label">in 2025</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Public Repositories</div>
                    <div class="stat-number">15</div>
                    <div class="stat-label">Projects</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Contribution Streak</div>
                    <div class="stat-number">🔥 24</div>
                    <div class="stat-label">Days</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Languages</div>
                    <div class="stat-number">8+</div>
                    <div class="stat-label">Technologies</div>
                </div>
            </div>
        </div>

        <!-- Contribution Graph -->
        <div class="section">
            <h2 class="section-title">CONTRIBUTION ACTIVITY</h2>
            <div class="contribution-graph">
                <p style="text-align: center; color: #8b949e;">155 contributions in the last year</p>
                <div class="graph-container" id="contributionGraph"></div>
            </div>
        </div>

        <!-- Tech Stack -->
        <div class="section">
            <h2 class="section-title">TECH STACK</h2>
            <h3 style="color: #00ff00; margin: 20px 0 10px 0;">Languages</h3>
            <div class="tech-grid">
                <div class="tech-badge">🐍 Python</div>
                <div class="tech-badge">C</div>
                <div class="tech-badge">C++</div>
                <div class="tech-badge">💻 Bash</div>
            </div>

            <h3 style="color: #00ff00; margin: 20px 0 10px 0;">DevOps & Cloud</h3>
            <div class="tech-grid">
                <div class="tech-badge">🐳 Docker</div>
                <div class="tech-badge">☁️ AWS</div>
                <div class="tech-badge">🐧 Linux</div>
                <div class="tech-badge">📦 Git</div>
            </div>

            <h3 style="color: #00ff00; margin: 20px 0 10px 0;">Databases</h3>
            <div class="tech-grid">
                <div class="tech-badge">🐘 PostgreSQL</div>
                <div class="tech-badge">🐬 MySQL</div>
                <div class="tech-badge">🍃 MongoDB</div>
                <div class="tech-badge">⚡ Redis</div>
            </div>

            <h3 style="color: #00ff00; margin: 20px 0 10px 0;">Frameworks</h3>
            <div class="tech-grid">
                <div class="tech-badge">Flask</div>
                <div class="tech-badge">FastAPI</div>
                <div class="tech-badge">⚛️ React</div>
                <div class="tech-badge">Node.js</div>
            </div>
        </div>

        <!-- Featured Projects -->
        <div class="section">
            <h2 class="section-title">FEATURED PROJECTS</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-title">🎵 KrivyX - Music Streaming</div>
                    <div class="project-desc">Next-generation music streaming platform with AI-powered recommendations and seamless user experience.</div>
                    <div class="project-tech">
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">Flask</span>
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">PostgreSQL</span>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-title">🔍 YOLOv8 Object Detection</div>
                    <div class="project-desc">Real-time object detection system using YOLOv8 with high accuracy and performance optimization.</div>
                    <div class="project-tech">
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">YOLOv8</span>
                        <span class="tech-tag">OpenCV</span>
                        <span class="tech-tag">TensorFlow</span>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-title">🎭 MoodMelody</div>
                    <div class="project-desc">Music recommendation system based on mood detection using machine learning algorithms.</div>
                    <div class="project-tech">
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">ML</span>
                        <span class="tech-tag">Spotify API</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Achievements -->
        <div class="section">
            <h2 class="section-title">ACHIEVEMENTS & RECOGNITION</h2>
            <div class="achievements">
                <div class="achievement-card">
                    <div class="achievement-icon">🏆</div>
                    <div class="achievement-title">Core Member</div>
                    <div class="achievement-desc">FOSS United Kanpur</div>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">🎨</div>
                    <div class="achievement-title">Lead Designer</div>
                    <div class="achievement-desc">FOSS Kanpur 2025</div>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">✅</div>
                    <div class="achievement-title">Google Arcade 2024</div>
                    <div class="achievement-desc">Finisher Badge</div>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">💻</div>
                    <div class="achievement-title">Open Source</div>
                    <div class="achievement-desc">Active Contributor</div>
                </div>
                <div class="achievement-card">
                    <div class="achievement-icon">🔒</div>
                    <div class="achievement-title">Cybersecurity</div>
                    <div class="achievement-desc">Security Researcher</div>
                </div>
            </div>
        </div>

        <!-- Contact Links -->
        <div class="section">
            <h2 class="section-title">CONNECT WITH ME</h2>
            <div class="contact-links">
                <a href="https://linkedin.com/in/krishna-tripathi-9aa494303" class="contact-btn" target="_blank">
                    💼 LinkedIn
                </a>
                <a href="https://github.com/Krishna-Tripathi78" class="contact-btn" target="_blank">
                    🐙 GitHub
                </a>
                <a href="https://x.com/KrishnaTri37551" class="contact-btn" target="_blank">
                    🐦 Twitter
                </a>
                <a href="https://www.hackerrank.com/profile/krishnatripathi9" class="contact-btn" target="_blank">
                    💡 HackerRank
                </a>
                <a href="mailto:krishnatripathi9@gmail.com" class="contact-btn">
                    📧 Email
                </a>
            </div>
        </div>

        <!-- Footer -->
        <div style="text-align: center; margin: 40px 0; color: #8b949e;">
            <p style="font-family: 'Courier New', monospace; color: #00ff00; font-size: 18px;">
                "Hack. Secure. Automate. Repeat." 🔒🚀
            </p>
            <p style="margin-top: 20px;">Made with 💚 by Krishna Tripathi</p>
        </div>
    </div>

    <script>
        // Typing Animation
        const texts = [
            "Hi 👋, I'm Krishna Tripathi",
            "Cybersecurity Engineer 🔒",
            "DevOps Enthusiast ☁️",
            "Open Source Contributor 💻",
            "Breaking Systems to Secure Them 🛡️"
        ];
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typingText');

        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentText.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
            }

            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }

        type();

        // Generate Contribution Graph
        const graphContainer = document.getElementById('contributionGraph');
        const totalCells = 371; // 53 weeks * 7 days
        
        for (let i = 0; i < totalCells; i++) {
            const cell = document.createElement('div');
            cell.className = 'graph-cell';
            
            // Randomly assign activity levels
            const random = Math.random();
            if (random > 0.7) cell.classList.add('active-4');
            else if (random > 0.5) cell.classList.add('active-3');
            else if (random > 0.3) cell.classList.add('active-2');
            else if (random > 0.15) cell.classList.add('active-1');
            
            graphContainer.appendChild(cell);
        }

        // Animate stats on scroll
        const statNumbers = document.querySelectorAll('.stat-number');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'none';
                    setTimeout(() => {
                        entry.target.style.animation = 'pulse 1s ease-in-out';
                    }, 10);
                }
            });
        });

        statNumbers.forEach(stat => observer.observe(stat));
    </script>
</body>
</html>
