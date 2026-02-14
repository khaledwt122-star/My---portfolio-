# My---portfolio-
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Khaled Walid Taibi - Portfolio Leadership</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Exo+2:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --neon-cyan: #00f3ff;
            --neon-purple: #bf00ff;
            --neon-pink: #ff006e;
            --neon-green: #00ff88;
            --neon-gold: #ffd700;
            --dark-void: #0a0014;
            --deep-purple: #1a0033;
            --glow-intensity: 20px;
        }

        body {
            font-family: 'Exo 2', sans-serif;
            background: var(--dark-void);
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
            position: relative;
        }

        /* Animated space background */
        .space-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(ellipse at center, var(--deep-purple) 0%, var(--dark-void) 70%);
            overflow: hidden;
        }

        /* Animated stars */
        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: twinkle var(--twinkle-duration) infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.5); }
        }

        /* Floating particles */
        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: var(--neon-cyan);
            border-radius: 50%;
            opacity: 0.6;
            filter: blur(1px);
            animation: float-particle 20s infinite linear;
        }

        @keyframes float-particle {
            0% {
                transform: translateY(100vh) translateX(0) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 0.6;
            }
            90% {
                opacity: 0.6;
            }
            100% {
                transform: translateY(-100px) translateX(100px) scale(1);
                opacity: 0;
            }
        }

        /* Main container */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }

        /* Header with profile */
        header {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 50px 20px;
            position: relative;
        }

        .profile-container {
            position: relative;
            margin-bottom: 40px;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .profile-ring {
            width: 320px;
            height: 320px;
            border-radius: 50%;
            background: conic-gradient(
                var(--neon-cyan) 0deg,
                var(--neon-purple) 120deg,
                var(--neon-pink) 240deg,
                var(--neon-cyan) 360deg
            );
            padding: 6px;
            position: relative;
            animation: rotate-ring 10s linear infinite;
            box-shadow: 
                0 0 50px var(--neon-cyan),
                0 0 100px var(--neon-purple),
                inset 0 0 30px rgba(191, 0, 255, 0.3);
        }

        @keyframes rotate-ring {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .profile-photo {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: linear-gradient(135deg, #1a1a2e, #0f0f1e);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            position: relative;
        }

        .profile-photo img {
            width: 110%;
            height: 110%;
            object-fit: cover;
            object-position: center 20%;
            transform: scale(1.15);
        }

        .leadership-badge {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            background: linear-gradient(135deg, var(--neon-gold), var(--neon-cyan));
            padding: 10px 25px;
            border-radius: 25px;
            font-family: 'Orbitron', sans-serif;
            font-size: 14px;
            font-weight: 700;
            color: var(--dark-void);
            box-shadow: 
                0 5px 20px rgba(255, 215, 0, 0.5),
                0 0 20px rgba(0, 243, 255, 0.3);
            animation: pulse-badge 2s infinite;
        }

        @keyframes pulse-badge {
            0%, 100% {
                transform: translateX(-50%) scale(1);
            }
            50% {
                transform: translateX(-50%) scale(1.05);
            }
        }

        .hero-title {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(40px, 8vw, 90px);
            font-weight: 900;
            margin-bottom: 15px;
            background: linear-gradient(90deg, var(--neon-cyan), var(--neon-purple), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: slide-in-left 1s ease-out;
            text-transform: uppercase;
            letter-spacing: 3px;
        }

        @keyframes slide-in-left {
            from {
                opacity: 0;
                transform: translateX(-100px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .hero-subtitle {
            font-size: clamp(20px, 3vw, 28px);
            color: var(--neon-cyan);
            margin-bottom: 10px;
            font-weight: 600;
            text-shadow: 0 0 20px var(--neon-cyan);
            animation: slide-in-right 1s ease-out 0.3s both;
        }

        @keyframes slide-in-right {
            from {
                opacity: 0;
                transform: translateX(100px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .hero-role {
            font-size: clamp(16px, 2vw, 22px);
            color: #cccccc;
            margin-bottom: 40px;
            animation: fade-in 1s ease-out 0.6s both;
        }

        @keyframes fade-in {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        .cta-container {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            animation: fade-in 1s ease-out 0.9s both;
        }

        .cta-button {
            position: relative;
            padding: 18px 45px;
            background: linear-gradient(135deg, var(--neon-purple), var(--neon-cyan));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 18px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 
                0 5px 30px rgba(191, 0, 255, 0.4),
                0 0 50px rgba(0, 243, 255, 0.3);
            border: 2px solid transparent;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s;
        }

        .cta-button:hover::before {
            left: 100%;
        }

        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 
                0 8px 40px rgba(191, 0, 255, 0.6),
                0 0 70px rgba(0, 243, 255, 0.5);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-10px);
            }
            60% {
                transform: translateX(-50%) translateY(-5px);
            }
        }

        .scroll-indicator span {
            display: block;
            width: 30px;
            height: 50px;
            border: 3px solid var(--neon-cyan);
            border-radius: 25px;
            position: relative;
        }

        .scroll-indicator span::before {
            content: '';
            position: absolute;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            width: 6px;
            height: 6px;
            background: var(--neon-cyan);
            border-radius: 50%;
            animation: scroll-down 2s infinite;
            box-shadow: 0 0 10px var(--neon-cyan);
        }

        @keyframes scroll-down {
            0% {
                opacity: 0;
                top: 10px;
            }
            50% {
                opacity: 1;
            }
            100% {
                opacity: 0;
                top: 30px;
            }
        }

        /* Sections */
        section {
            padding: 120px 20px;
            position: relative;
        }

        .section-title {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(35px, 6vw, 60px);
            text-align: center;
            margin-bottom: 70px;
            background: linear-gradient(90deg, var(--neon-cyan), var(--neon-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-transform: uppercase;
            letter-spacing: 2px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, var(--neon-cyan), var(--neon-purple));
            border-radius: 2px;
            box-shadow: 0 0 20px var(--neon-cyan);
        }

        /* Experience Timeline */
        .timeline {
            position: relative;
            max-width: 1200px;
            margin: 0 auto;
            padding-left: 50px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 4px;
            background: linear-gradient(180deg, var(--neon-cyan), var(--neon-purple), var(--neon-pink));
            border-radius: 2px;
            box-shadow: 0 0 20px var(--neon-cyan);
        }

        .timeline-item {
            position: relative;
            margin-bottom: 60px;
            padding-left: 50px;
            opacity: 0;
            transform: translateX(50px);
            transition: all 0.6s ease;
        }

        .timeline-item.active {
            opacity: 1;
            transform: translateX(0);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -8px;
            top: 0;
            width: 20px;
            height: 20px;
            background: var(--neon-cyan);
            border: 4px solid var(--dark-void);
            border-radius: 50%;
            box-shadow: 0 0 20px var(--neon-cyan);
            z-index: 1;
        }

        .timeline-content {
            background: rgba(26, 0, 51, 0.4);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(191, 0, 255, 0.3);
            border-radius: 20px;
            padding: 30px;
            transition: all 0.3s ease;
        }

        .timeline-content:hover {
            border-color: var(--neon-cyan);
            box-shadow: 0 10px 40px rgba(0, 243, 255, 0.3);
            transform: translateY(-5px);
        }

        .timeline-date {
            color: var(--neon-gold);
            font-weight: 700;
            font-size: 14px;
            margin-bottom: 10px;
            text-shadow: 0 0 10px var(--neon-gold);
        }

        .timeline-title {
            font-family: 'Orbitron', sans-serif;
            font-size: 24px;
            color: var(--neon-cyan);
            margin-bottom: 8px;
            font-weight: 700;
        }

        .timeline-company {
            font-size: 18px;
            color: var(--neon-purple);
            margin-bottom: 15px;
            font-weight: 600;
        }

        .timeline-description {
            color: #cccccc;
            line-height: 1.8;
            margin-bottom: 15px;
        }

        .timeline-tasks {
            list-style: none;
            padding-left: 0;
        }

        .timeline-tasks li {
            color: #aaaaaa;
            padding: 8px 0;
            padding-left: 30px;
            position: relative;
        }

        .timeline-tasks li::before {
            content: '▹';
            position: absolute;
            left: 0;
            color: var(--neon-cyan);
            font-size: 20px;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .skill-item {
            background: rgba(26, 0, 51, 0.4);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(191, 0, 255, 0.3);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
            opacity: 0;
            transform: scale(0.8);
        }

        .skill-item.active {
            opacity: 1;
            transform: scale(1);
        }

        .skill-item:hover {
            border-color: var(--neon-cyan);
            box-shadow: 0 10px 40px rgba(0, 243, 255, 0.3);
            transform: translateY(-10px) scale(1.05);
        }

        .skill-name {
            font-size: 18px;
            font-weight: 600;
            color: #ffffff;
            margin-bottom: 10px;
        }

        /* Diplomas & Certifications */
        .diplomas-grid,
        .certifications-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .diploma-card,
        .cert-card {
            background: rgba(26, 0, 51, 0.4);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(191, 0, 255, 0.3);
            border-radius: 20px;
            padding: 35px;
            transition: all 0.3s ease;
            opacity: 0;
            transform: translateY(50px);
        }

        .diploma-card.active,
        .cert-card.active {
            opacity: 1;
            transform: translateY(0);
        }

        .diploma-card:hover,
        .cert-card:hover {
            border-color: var(--neon-cyan);
            box-shadow: 0 15px 50px rgba(0, 243, 255, 0.3);
            transform: translateY(-10px);
        }

        .diploma-icon,
        .cert-icon {
            font-size: 50px;
            margin-bottom: 20px;
            filter: drop-shadow(0 0 10px var(--neon-gold));
        }

        .diploma-title,
        .cert-title {
            font-family: 'Orbitron', sans-serif;
            font-size: 24px;
            color: var(--neon-cyan);
            margin-bottom: 12px;
            font-weight: 700;
        }

        .diploma-org,
        .cert-org {
            color: var(--neon-purple);
            font-weight: 600;
            margin-bottom: 8px;
            font-size: 16px;
        }

        .diploma-date,
        .cert-date {
            color: var(--neon-gold);
            font-weight: 600;
            margin-bottom: 20px;
            font-size: 14px;
        }

        .diploma-details,
        .cert-details {
            color: #cccccc;
            line-height: 1.8;
        }

        .diploma-details p,
        .cert-details p {
            margin-bottom: 8px;
        }

        .diploma-id,
        .cert-id {
            color: var(--neon-cyan) !important;
            font-family: 'Courier New', monospace;
            font-size: 13px;
            margin-top: 15px;
        }

        /* Footer */
        footer {
            background: rgba(10, 0, 20, 0.9);
            padding: 40px 20px;
            text-align: center;
            border-top: 2px solid rgba(191, 0, 255, 0.3);
        }

        footer p {
            color: #999999;
            font-size: 14px;
        }

        /* Reveal animations */
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.6s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .profile-ring {
                width: 250px;
                height: 250px;
            }

            .timeline {
                padding-left: 30px;
            }

            .timeline-item {
                padding-left: 30px;
            }

            .skills-grid,
            .diplomas-grid,
            .certifications-grid {
                grid-template-columns: 1fr;
            }

            section {
                padding: 80px 15px;
            }

            .cta-container {
                flex-direction: column;
                align-items: center;
            }

            .cta-button {
                width: 100%;
                max-width: 300px;
            }
        }

        @media (max-width: 480px) {
            .profile-ring {
                width: 200px;
                height: 200px;
            }

            .hero-title {
                font-size: 32px;
            }

            .hero-subtitle {
                font-size: 18px;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Space Background -->
    <div class="space-bg" id="spaceBg"></div>

    <!-- Header Section -->
    <header>
        <div class="profile-container">
            <div class="profile-ring">
                <div class="profile-photo">
                    <img src="https://i.ibb.co/ZV9DQGm/IMG-20240908-012524.jpg" alt="Khaled Walid Taibi">
                </div>
            </div>
            <div class="leadership-badge">LEADER • INNOVATEUR</div>
        </div>

        <h1 class="hero-title">Khaled Walid Taibi</h1>
        <p class="hero-subtitle">Management Leadership • Marketing Digital</p>
        <p class="hero-role">Expert en Stratégie & Innovation | Multilingue (Français • Anglais • Arabe)</p>

        <div class="cta-container">
            <a href="#experience" class="cta-button">
                <span>Décou
