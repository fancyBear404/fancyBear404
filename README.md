<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fancyBear Community</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #0a1a0a;
            color: #e0ffe0;
            line-height: 1.6;
            padding: 20px;
            position: relative;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        /* Enhanced Animated GIF Background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://i.pinimg.com/originals/96/74/a3/9674a3ff21e02af82daa565e5773fa56.gif') center/cover no-repeat;
            opacity: 0.4;
            z-index: -1;
            pointer-events: none;
        }
        
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(10, 26, 10, 0.85), rgba(10, 26, 10, 0.6));
            z-index: -1;
            pointer-events: none;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }
        
        header {
            text-align: center;
            padding: 40px 0;
            margin-bottom: 30px;
        }
        
        h1 {
            font-size: 3.5rem;
            background: linear-gradient(to right, #7aff7a, #00ff00, #7aff7a);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 20px;
            text-shadow: 0 0 15px rgba(0, 255, 0, 0.5);
        }
        
        h2, h3 {
            color: #aaffaa;
            margin: 25px 0 15px;
            text-align: center;
        }
        
        .important-note {
            background: linear-gradient(to right, rgba(26, 58, 26, 0.9), rgba(42, 90, 42, 0.9));
            border-left: 4px solid #00ff00;
            padding: 20px;
            border-radius: 8px;
            margin: 30px 0;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
        }
        
        .github-link {
            display: block;
            text-align: center;
            font-size: 1.2rem;
            margin: 20px 0;
            color: #7aff7a;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .github-link:hover {
            color: #00ff00;
            text-decoration: underline;
            transform: scale(1.05);
        }
        
        .telegram-button {
            display: inline-block;
            background: linear-gradient(to right, #00cc00, #009900);
            color: white;
            padding: 12px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            margin: 15px 0;
            transition: all 0.3s ease;
            box-shadow: 0 4px 10px rgba(0, 204, 0, 0.4);
        }
        
        .telegram-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(0, 204, 0, 0.6);
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }
        
        .skill-item {
            text-align: center;
            background: rgba(20, 50, 20, 0.7);
            padding: 15px 10px;
            border-radius: 10px;
            transition: all 0.3s ease;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(0, 255, 0, 0.3);
        }
        
        .skill-item:hover {
            transform: scale(1.1);
            background: rgba(30, 70, 30, 0.8);
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
        }
        
        .skill-item i {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }
        
        .python { color: #3776ab; }
        .javascript { color: #f7df1e; }
        .java { color: #007396; }
        .perl { color: #39457e; }
        .redhat { color: #e00; }
        .php { color: #777bb4; }
        .cplusplus { color: #00599c; }
        .csharp { color: #239120; }
        
        .snake-animation {
            width: 100%;
            height: 100px;
            margin: 50px 0;
            background: rgba(15, 30, 15, 0.7);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            border: 1px solid rgba(0, 255, 0, 0.3);
        }
        
        .snake {
            position: absolute;
            top: 50%;
            left: 0;
            transform: translateY(-50%);
            width: 100%;
            height: 4px;
            background: linear-gradient(to right, transparent, #00ff00, transparent);
            animation: snakeMove 3s linear infinite;
        }
        
        @keyframes snakeMove {
            0% { left: -100%; }
            100% { left: 100%; }
        }
        
        .pacman-graph {
            width: 100%;
            height: 200px;
            background: rgba(15, 30, 15, 0.7);
            border-radius: 10px;
            margin: 50px 0;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(0, 255, 0, 0.3);
        }
        
        .pacman {
            position: absolute;
            top: 50%;
            left: 50px;
            width: 40px;
            height: 40px;
            background: #ff0;
            border-radius: 50%;
            animation: eat 1s infinite linear;
            transform: translateY(-50%);
        }
        
        @keyframes eat {
            0% { clip-path: polygon(50% 50%, 0 0, 0 100%); }
            50% { clip-path: polygon(50% 50%, 0 0, 100% 0, 100% 100%, 0 100%); }
            100% { clip-path: polygon(50% 50%, 100% 0, 100% 100%); }
        }
        
        .dot {
            position: absolute;
            top: 50%;
            width: 10px;
            height: 10px;
            background: #ff0;
            border-radius: 50%;
            transform: translateY(-50%);
        }
        
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            border-top: 1px solid rgba(42, 90, 42, 0.5);
            color: #aaffaa;
            background: rgba(10, 26, 10, 0.7);
            border-radius: 8px;
            backdrop-filter: blur(5px);
        }
        
        .cyber-border {
            position: fixed;
            pointer-events: none;
            z-index: 100;
        }
        
        .border-top {
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(to right, #7aff7a, #00ff00, #7aff7a);
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.7);
        }
        
        .border-right {
            top: 0;
            right: 0;
            width: 2px;
            height: 100%;
            background: linear-gradient(to bottom, #7aff7a, #00ff00, #7aff7a);
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.7);
        }
        
        .border-bottom {
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(to right, #7aff7a, #00ff00, #7aff7a);
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.7);
        }
        
        .border-left {
            top: 0;
            left: 0;
            width: 2px;
            height: 100%;
            background: linear-gradient(to bottom, #7aff7a, #00ff00, #7aff7a);
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.7);
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(70px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="cyber-border border-top"></div>
    <div class="cyber-border border-right"></div>
    <div class="cyber-border border-bottom"></div>
    <div class="cyber-border border-left"></div>
    
    <div class="overlay"></div>
    
    <div class="container">
        <header>
            <h1>Welcome to fancyBear community</h1>
        </header>
        
        <section>
            <div class="important-note">
                <h3>[!!] Important Information</h3>
                <p>Save or follow our GitHub link to not lose contact with fancyBear.</p>
                <p>If Telegram deletes our community, you will find update links here.</p>
                <a href="https://github.com/fancyBear404" class="github-link">
                    <i class="fab fa-github"></i> https://github.com/fancyBear404
                </a>
            </div>
        </section>
        
        <section>
            <h3>Channel free leaked database:</h3>
            <div style="text-align: center;">
                <a href="https://t.me/+4Gtbq_k53tM4NDE0" class="telegram-button">
                    <i class="fab fa-telegram"></i> Join Telegram Channel
                </a>
            </div>
        </section>
        
        <section>
            <h3>Experience from 1983 on:</h3>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-python python"></i>
                    <p>Python</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-js javascript"></i>
                    <p>JavaScript</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-java java"></i>
                    <p>Java</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-perl perl"></i>
                    <p>Perl</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-redhat redhat"></i>
                    <p>RedHat</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-php php"></i>
                    <p>PHP</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-cuttlefish cplusplus"></i>
                    <p>C++</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-microsoft csharp"></i>
                    <p>C#</p>
                </div>
            </div>
        </section>
        
        <div class="snake-animation">
            <div class="snake"></div>
        </div>
        
        <div class="pacman-graph">
            <div class="pacman"></div>
            <div class="dot" style="left: 120px;"></div>
            <div class="dot" style="left: 180px;"></div>
            <div class="dot" style="left: 240px;"></div>
            <div class="dot" style="left: 300px;"></div>
            <div class="dot" style="left: 360px;"></div>
            <div class="dot" style="left: 420px;"></div>
            <div class="dot" style="left: 480px;"></div>
            <div class="dot" style="left: 540px;"></div>
            <div class="dot" style="left: 600px;"></div>
            <div class="dot" style="left: 660px;"></div>
            <div class="dot" style="left: 720px;"></div>
        </div>
        
        <footer>
            <p>© 1983 fancyBear Community. All rights reserved.</p>
        </footer>
    </div>
    
    <script>
        // Add some interactive effects
        document.addEventListener('DOMContentLoaded', function() {
            const skillItems = document.querySelectorAll('.skill-item');
            
            skillItems.forEach(item => {
                item.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.1) translateY(-5px)';
                });
                
                item.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1)';
                });
            });
            
            // Animate elements on scroll
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);
            
            const animatedElements = document.querySelectorAll('.important-note, .skill-item, .snake-animation, .pacman-graph');
            animatedElements.forEach(el => {
                el.style.opacity = 0;
                el.style.transform = 'translateY(20px)';
                el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                observer.observe(el);
            });
        });
    </script>
</body>
</html>
