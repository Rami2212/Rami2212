<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ramitha Iddamalgoda - Full Stack Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 40px 20px;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        /* Interactive Title Section */
        .title-section {
            text-align: center;
            margin-bottom: 50px;
            animation: fadeInDown 0.8s ease-out;
        }

        .title-section h1 {
            font-size: 4em;
            background: linear-gradient(135deg, #667eea, #764ba2, #f093fb, #4facfe);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease infinite, floatText 3s ease-in-out infinite;
            margin-bottom: 10px;
            font-weight: 800;
        }

        .subtitle {
            font-size: 1.3em;
            color: white;
            margin-bottom: 25px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            animation: fadeInUp 0.8s ease-out 0.2s both;
        }

        /* Social Icons */
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 30px;
            animation: fadeInUp 0.8s ease-out 0.4s both;
        }

        .social-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            transition: all 0.3s ease;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            position: relative;
            overflow: hidden;
        }

        .social-icon::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: rgba(255,255,255,0.2);
            transition: left 0.3s ease;
            z-index: -1;
        }

        .social-icon:hover::before {
            left: 100%;
        }

        .github-icon {
            background: #333;
            color: white;
        }

        .github-icon:hover {
            transform: translateY(-5px) scale(1.1);
            background: #1a1a1a;
        }

        .linkedin-icon {
            background: #0077B5;
            color: white;
        }

        .linkedin-icon:hover {
            transform: translateY(-5px) scale(1.1);
            background: #005885;
        }

        .gmail-icon {
            background: #EA4335;
            color: white;
        }

        .gmail-icon:hover {
            transform: translateY(-5px) scale(1.1);
            background: #c5221f;
        }

        .portfolio-icon {
            background: #FF6B6B;
            color: white;
        }

        .portfolio-icon:hover {
            transform: translateY(-5px) scale(1.1);
            background: #ee5a52;
        }

        /* Skills Section */
        .section {
            background: white;
            border-radius: 15px;
            padding: 35px;
            margin-bottom: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.15);
            animation: fadeInUp 0.8s ease-out;
        }

        .section h2 {
            font-size: 2em;
            color: #667eea;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skill-category {
            margin-bottom: 25px;
        }

        .skill-category h3 {
            font-size: 1.2em;
            color: #764ba2;
            margin-bottom: 15px;
            font-weight: 600;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 15px;
        }

        .skill-icon {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 15px;
            background: linear-gradient(135deg, #667eea20, #764ba220);
            border-radius: 10px;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 2px solid transparent;
            min-height: 100px;
        }

        .skill-icon:hover {
            transform: translateY(-8px) scale(1.05);
            background: linear-gradient(135deg, #667eea30, #764ba230);
            border-color: #667eea;
            box-shadow: 0 8px 20px rgba(102, 126, 234, 0.3);
        }

        .skill-icon i {
            font-size: 2.5em;
            margin-bottom: 8px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .skill-icon span {
            font-size: 0.85em;
            font-weight: 600;
            text-align: center;
            color: #333;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .project-card {
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 12px;
            padding: 20px;
            color: white;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 100%;
            height: 100%;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            transition: all 0.5s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.4);
        }

        .project-card:hover::before {
            top: -25%;
            right: -25%;
        }

        .project-title {
            font-size: 1.3em;
            font-weight: 700;
            margin-bottom: 12px;
            position: relative;
            z-index: 1;
        }

        .project-desc {
            font-size: 0.95em;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
            line-height: 1.6;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            position: relative;
            z-index: 1;
        }

        .tech-badge {
            background: rgba(255,255,255,0.25);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85em;
            border: 1px solid rgba(255,255,255,0.4);
            transition: all 0.3s ease;
        }

        .tech-badge:hover {
            background: rgba(255,255,255,0.35);
            transform: scale(1.05);
        }

        /* Analytics Section */
        .analytics {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .analytics-card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 10px 40px rgba(0,0,0,0.15);
            transition: all 0.3s ease;
        }

        .analytics-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 50px rgba(102, 126, 234, 0.25);
        }

        .analytics-card h3 {
            color: #667eea;
            font-size: 1.1em;
            margin-bottom: 15px;
        }

        .analytics-badge {
            display: inline-block;
            margin-top: 10px;
        }

        /* Animations */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes floatText {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        @media (max-width: 768px) {
            .title-section h1 {
                font-size: 2.5em;
            }

            .subtitle {
                font-size: 1em;
            }

            .skills-grid {
                grid-template-columns: repeat(auto-fill, minmax(70px, 1fr));
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Interactive Title -->
        <div class="title-section">
            <h1>✨ Ramitha Iddamalgoda</h1>
            <p class="subtitle">Full Stack Developer | Cloud Architect | Mobile Developer</p>
            
            <!-- Social Icons -->
            <div class="social-icons">
                <a class="social-icon github-icon" href="https://github.com/Rami2212" target="_blank" title="GitHub">
                    <i class="fab fa-github"></i>
                </a>
                <a class="social-icon linkedin-icon" href="https://www.linkedin.com/in/ramitha-iddamalgoda/" target="_blank" title="LinkedIn">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a class="social-icon gmail-icon" href="mailto:ramithapathmilarp@gmail.com" title="Email">
                    <i class="fas fa-envelope"></i>
                </a>
                <a class="social-icon portfolio-icon" href="#" title="Portfolio">
                    <i class="fas fa-globe"></i>
                </a>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="section">
            <h2><i class="fas fa-code"></i> Tech Stack & Skills</h2>

            <div class="skill-category">
                <h3>💻 Core Languages</h3>
                <div class="skills-grid">
                    <div class="skill-icon"><i class="fab fa-java"></i><span>Java</span></div>
                    <div class="skill-icon"><i class="fab fa-js-square"></i><span>JavaScript</span></div>
                    <div class="skill-icon"><i class="fab fa-js-square"></i><span>TypeScript</span></div>
                    <div class="skill-icon"><i class="fab fa-python"></i><span>Python</span></div>
                    <div class="skill-icon"><i class="fas fa-code"></i><span>Dart</span></div>
                    <div class="skill-icon"><i class="fas fa-code"></i><span>Kotlin</span></div>
                    <div class="skill-icon"><i class="fas fa-code"></i><span>C</span></div>
                </div>
            </div>

            <div class="skill-category">
                <h3>🚀 Backend & Frameworks</h3>
                <div class="skills-grid">
                    <div class="skill-icon"><i class="fab fa-java"></i><span>Spring Boot</span></div>
                    <div class="skill-icon"><i class="fab fa-node-js"></i><span>Node.js</span></div>
                    <div class="skill-icon"><i class="fab fa-js-square"></i><span>Express</span></div>
                    <div class="skill-icon"><i class="fas fa-lock"></i><span>OAuth2/OIDC</span></div>
                    <div class="skill-icon"><i class="fas fa-key"></i><span>Keycloak</span></div>
                    <div class="skill-icon"><i class="fas fa-stream"></i><span>Kafka</span></div>
                </div>
            </div>

            <div class="skill-category">
                <h3>🎨 Frontend & Mobile</h3>
                <div class="skills-grid">
                    <div class="skill-icon"><i class="fab fa-react"></i><span>React</span></div>
                    <div class="skill-icon"><i class="fas fa-arrow-right"></i><span>Next.js</span></div>
                    <div class="skill-icon"><i class="fab fa-angular"></i><span>Angular</span></div>
                    <div class="skill-icon"><i class="fas fa-palette"></i><span>Flutter</span></div>
                    <div class="skill-icon"><i class="fab fa-html5"></i><span>HTML/CSS</span></div>
                    <div class="skill-icon"><i class="fas fa-redo"></i><span>Redux</span></div>
                </div>
            </div>

            <div class="skill-category">
                <h3>🗄️ Databases & Cloud</h3>
                <div class="skills-grid">
                    <div class="skill-icon"><i class="fas fa-database"></i><span>MySQL</span></div>
                    <div class="skill-icon"><i class="fas fa-database"></i><span>PostgreSQL</span></div>
                    <div class="skill-icon"><i class="fas fa-leaf"></i><span>MongoDB</span></div>
                    <div class="skill-icon"><i class="fas fa-fire"></i><span>Firebase</span></div>
                    <div class="skill-icon"><i class="fab fa-aws"></i><span>AWS</span></div>
                    <div class="skill-icon"><i class="fas fa-cloud"></i><span>Azure</span></div>
                </div>
            </div>

            <div class="skill-category">
                <h3>🐳 DevOps & Tools</h3>
                <div class="skills-grid">
                    <div class="skill-icon"><i class="fab fa-docker"></i><span>Docker</span></div>
                    <div class="skill-icon"><i class="fas fa-cubes"></i><span>Kubernetes</span></div>
                    <div class="skill-icon"><i class="fab fa-github"></i><span>GitHub Actions</span></div>
                    <div class="skill-icon"><i class="fas fa-rocket"></i><span>ArgoCD</span></div>
                    <div class="skill-icon"><i class="fas fa-code"></i><span>Concourse CI</span></div>
                    <div class="skill-icon"><i class="fas fa-brain"></i><span>TensorFlow</span></div>
                </div>
            </div>

            <div class="skill-category">
                <h3>🎯 Design & Additional Tools</h3>
                <div class="skills-grid">
                    <div class="skill-icon"><i class="fab fa-figma"></i><span>Figma</span></div>
                    <div class="skill-icon"><i class="fab fa-adobe"></i><span>Photoshop</span></div>
                    <div class="skill-icon"><i class="fas fa-palette"></i><span>Canva</span></div>
                    <div class="skill-icon"><i class="fas fa-gamepad"></i><span>Unreal Engine</span></div>
                    <div class="skill-icon"><i class="fas fa-cube"></i><span>Unity</span></div>
                    <div class="skill-icon"><i class="fab fa-git-alt"></i><span>Git/GitHub</span></div>
                </div>
            </div>
        </div>

        <!-- Projects Section -->
        <div class="section">
            <h2><i class="fas fa-project-diagram"></i> Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-title">🛍️ Mobile Store</div>
                    <div class="project-desc">Comprehensive e-commerce microservice platform with secure authentication and orchestrated deployment.</div>
                    <div class="project-tech">
                        <span class="tech-badge">Spring Boot</span>
                        <span class="tech-badge">Kafka</span>
                        <span class="tech-badge">Angular</span>
                        <span class="tech-badge">Keycloak</span>
                        <span class="tech-badge">Docker</span>
                        <span class="tech-badge">Kubernetes</span>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-title">💻 Laptop Store</div>
                    <div class="project-desc">Full-stack e-commerce application with modern frontend framework and cloud deployment on Azure.</div>
                    <div class="project-tech">
                        <span class="tech-badge">Express.js</span>
                        <span class="tech-badge">React</span>
                        <span class="tech-badge">Redux</span>
                        <span class="tech-badge">Docker</span>
                        <span class="tech-badge">Azure</span>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-title">📢 AdvertisementLK</div>
                    <div class="project-desc">Dynamic advertisement platform connecting businesses with users across digital channels.</div>
                    <div class="project-tech">
                        <span class="tech-badge">Express.js</span>
                        <span class="tech-badge">React</span>
                        <span class="tech-badge">Redux</span>
                        <span class="tech-badge">Docker</span>
                        <span class="tech-badge">DigitalOcean</span>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-title">🤖 Object Detector App</div>
                    <div class="project-desc">Mobile application leveraging TensorFlow for real-time object detection and recognition.</div>
                    <div class="project-tech">
                        <span class="tech-badge">Flutter</span>
                        <span class="tech-badge">Dart</span>
                        <span class="tech-badge">TensorFlow</span>
                        <span class="tech-badge">AI/ML</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Analytics Section -->
        <div class="analytics">
            <div class="analytics-card">
                <h3>📊 GitHub Stats</h3>
                <div class="analytics-badge">
                    <img src="https://github-readme-stats.vercel.app/api?username=Rami2212&show_icons=true&theme=radical" alt="GitHub Stats">
                </div>
            </div>
            <div class="analytics-card">
                <h3>🏆 GitHub Trophies</h3>
                <div class="analytics-badge">
                    <img src="https://github-profile-trophy.vercel.app/?username=Rami2212&theme=radical&row=1&column=6" alt="GitHub Trophies">
                </div>
            </div>
        </div>

        <!-- Footer Section -->
        <div class="section" style="text-align: center;">
            <p style="color: #667eea; font-size: 1.1em; margin-bottom: 15px;">
                <i class="fas fa-lightbulb"></i> Always open to new opportunities, collaborations, and interesting projects
            </p>
            <p style="color: #764ba2; font-size: 0.95em;">
                Let's build something amazing together! Feel free to reach out.
            </p>
        </div>
    </div>
</body>
</html>
