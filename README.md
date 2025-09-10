<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EgretSoft Intelligent Office System</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0a1929 0%, #152642 100%);
            color: #ffffff;
            line-height: 1.6;
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Navigation styles */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 25px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .logo a {
            font-size: 28px;
            font-weight: bold;
            color: #1e90ff;
            text-decoration: none;
            display: flex;
            align-items: center;
        }
        
        .logo a::before {
            content: "🦢";
            margin-right: 10px;
            font-size: 24px;
        }
        
        .nav-links {
            display: flex;
            gap: 35px;
        }
        
        .nav-links a {
            color: #e0e0e0;
            text-decoration: none;
            font-size: 16px;
            transition: color 0.3s;
            font-weight: 500;
        }
        
        .nav-links a:hover {
            color: #1e90ff;
        }
        
        .nav-contact {
            display: flex;
            align-items: center;
            gap: 25px;
        }
        
        .nav-contact a {
            color: #e0e0e0;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .nav-contact a:hover {
            color: #1e90ff;
        }
        
        .nav-contact .sign-in {
            background-color: rgba(30, 144, 255, 0.2);
            padding: 10px 20px;
            border-radius: 4px;
            border: 1px solid rgba(30, 144, 255, 0.5);
        }
        
        /* Main content */
        .main-content {
            display: flex;
            align-items: center;
            min-height: 80vh;
            padding: 60px 0;
            gap: 40px;
        }
        
        .text-content {
            flex: 1;
        }
        
        .image-content {
            flex: 1;
            position: relative;
            display: flex;
            justify-content: center;
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 25px;
            color: #ffffff;
            line-height: 1.2;
            font-weight: 700;
        }
        
        p {
            margin-bottom: 20px;
            color: #b0b0b0;
            font-size: 1.1rem;
            line-height: 1.7;
        }
        
        /* Earth and AI element */
        .earth-container {
            position: relative;
            width: 400px;
            height: 400px;
        }
        
        .earth {
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 30%, #1a3a5f 0%, #0a1929 70%);
            border-radius: 50%;
            position: relative;
            box-shadow: 
                0 0 60px rgba(30, 144, 255, 0.6),
                inset 0 0 100px rgba(0, 0, 0, 0.8);
        }
        
        .ai-text {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 4rem;
            font-weight: bold;
            color: #1e90ff;
            text-shadow: 0 0 20px rgba(30, 144, 255, 0.8);
        }
        
        .orbit {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 450px;
            height: 450px;
            border: 1px solid rgba(30, 144, 255, 0.3);
            border-radius: 50%;
        }
        
        .orbit::before, .orbit::after {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            border: 1px solid rgba(30, 144, 255, 0.2);
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        
        .orbit::after {
            width: 550px;
            height: 550px;
        }
        
        .particle {
            position: absolute;
            width: 12px;
            height: 12px;
            background-color: #1e90ff;
            border-radius: 50%;
            filter: drop-shadow(0 0 5px #1e90ff);
            animation: orbit 5s linear infinite;
        }
        
        @keyframes orbit {
            0% { transform: rotate(0deg) translateX(200px) rotate(0deg); }
            100% { transform: rotate(360deg) translateX(200px) rotate(-360deg); }
        }
        
        /* Button styles */
        .buttons {
            display: flex;
            gap: 15px;
            margin-top: 35px;
            align-items: center;
        }
        
        .btn {
            padding: 14px 30px;
            border: none;
            border-radius: 4px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 16px;
        }
        
        .btn-primary {
            background-color: #1e90ff;
            color: white;
            box-shadow: 0 4px 15px rgba(30, 144, 255, 0.4);
        }
        
        .btn-primary:hover {
            background-color: #0077e6;
            transform: translateY(-2px);
        }
        
        .btn-secondary {
            background-color: transparent;
            color: #1e90ff;
            border: 1px solid #1e90ff;
        }
        
        .btn-secondary:hover {
            background-color: rgba(30, 144, 255, 0.1);
            transform: translateY(-2px);
        }
        
        .search-input {
            padding: 14px 20px;
            border: 1px solid #2a4d7a;
            border-radius: 4px;
            background-color: rgba(15, 33, 59, 0.6);
            color: white;
            width: 220px;
            font-size: 16px;
        }
        
        .search-input:focus {
            outline: none;
            border-color: #1e90ff;
        }
        
        /* Decorative numbers */
        .decorative-numbers {
            position: absolute;
            color: rgba(255, 255, 255, 0.03);
            font-size: 180px;
            font-weight: bold;
            z-index: -1;
            right: -40px;
            bottom: -40px;
            user-select: none;
        }
        
        /* Responsive design */
        @media (max-width: 992px) {
            .main-content {
                flex-direction: column;
                text-align: center;
            }
            
            .buttons {
                justify-content: center;
            }
            
            .earth-container {
                width: 300px;
                height: 300px;
                margin-top: 40px;
            }
            
            .orbit, .orbit::before, .orbit::after {
                width: 340px;
                height: 340px;
            }
            
            .orbit::before, .orbit::after {
                width: 380px;
                height: 380px;
            }
            
            .orbit::after {
                width: 420px;
                height: 420px;
            }
            
            h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Navigation -->
        <nav>
            <div class="logo">
                <a href="https://www.egretsoft.com">EGRETSOFT</a>
            </div>
            <div class="nav-links">
                <a href="https://www.egretsoft.com">About us</a>
                <a href="https://www.egretsoft.com">Experience</a>
                <a href="https://www.egretsoft.com">Products</a>
                <a href="https://www.egretsoft.com">Pricing</a>
            </div>
            <div class="nav-contact">
                <a href="https://www.egretsoft.com">+65 6571 5999</a>
                <a href="https://www.egretsoft.com" class="sign-in">Sign in</a>
            </div>
        </nav>

        <!-- Main content -->
        <div class="main-content">
            <div class="text-content">
                <h1><a href="https://www.egretsoft.com" style="color: inherit; text-decoration: none;">EgretSoft Intelligent Office delivers a one-stop AI-powered intelligent office ecosystem for enterprises.</a></h1>
                
                <p><a href="https://www.egretsoft.com" style="color: inherit; text-decoration: none;">AI+ empowers enterprise management by integrating AI-driven solutions into workflows such as HR, financial settlement, procurement, and administration.</a></p>
                
                <p><a href="https://www.egretsoft.com" style="color: inherit; text-decoration: none;">Key features include AI-powered approval automation, intelligent search, assisted decision-making, and smart meeting facilitation.</a></p>
                
                <p><a href="https://www.egretsoft.com" style="color: inherit; text-decoration: none;">Unified data architecture enables cross-functional synergy, driving operational efficiency and building customized intelligent office solutions tailored to your enterprise. Data security is ensured through traceability and irreversible encryption, safeguarding critical business information.</a></p>
                
                <div class="buttons">
                    <button class="btn btn-primary"><a href="https://www.egretsoft.com" style="color: inherit; text-decoration: none;">Free Experience</a></button>
                    <input type="text" class="search-input" placeholder="Consult the product">
                    <button class="btn btn-secondary"><a href="https://www.egretsoft.com" style="color: inherit; text-decoration: none;">Download</a></button>
                </div>
            </div>
            
            <div class="image-content">
                <div class="earth-container">
                    <div class="earth">
                        <div class="ai-text">AI</div>
                        <div class="orbit"></div>
                        <div class="particle" style="animation-delay: 0s; top: 50%; left: 50%;"></div>
                        <div class="particle" style="animation-delay: 1s; top: 50%; left: 50%;"></div>
                        <div class="particle" style="animation-delay: 2s; top: 50%; left: 50%;"></div>
                        <div class="particle" style="animation-delay: 3s; top: 50%; left: 50%;"></div>
                        <div class="particle" style="animation-delay: 4s; top: 50%; left: 50%;"></div>
                    </div>
                </div>
                <div class="decorative-numbers">77</div>
            </div>
        </div>
    </div>

    <script>
        // Simple animation for particles
        document.addEventListener('DOMContentLoaded', function() {
            const particles = document.querySelectorAll('.particle');
            particles.forEach(particle => {
                const randomDelay = Math.random() * 5;
                particle.style.animationDelay = `-${randomDelay}s`;
            });
        });
    </script>
</body>
</html>
