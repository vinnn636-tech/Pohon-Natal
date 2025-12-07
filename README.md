# Pohon-Natal
Animasi pohon natal
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Christmas Tree with Floating Gifts and Snow</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(to bottom, #001122, #000000);
            margin: 0;
            font-family: Arial, sans-serif;
            overflow: hidden;
            position: relative;
        }
        .floating-gifts {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .gift {
            position: absolute;
            font-size: 24px;
            animation: float 4s ease-in-out infinite;
        }
        .gift:nth-child(1) { top: 10%; left: 10%; animation-delay: 0s; }
        .gift:nth-child(2) { top: 20%; right: 15%; animation-delay: 1s; }
        .gift:nth-child(3) { top: 30%; left: 20%; animation-delay: 2s; }
        .gift:nth-child(4) { top: 40%; right: 10%; animation-delay: 0.5s; }
        .gift:nth-child(5) { top: 50%; left: 30%; animation-delay: 1.5s; }
        .gift:nth-child(6) { top: 60%; right: 20%; animation-delay: 2.5s; }
        .gift:nth-child(7) { top: 70%; left: 15%; animation-delay: 0.8s; }
        .gift:nth-child(8) { top: 80%; right: 25%; animation-delay: 1.2s; }
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
        }
        .snow {
            position: absolute;
            top: -10px;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .snowflake {
            position: absolute;
            width: 5px;
            height: 5px;
            background: white;
            border-radius: 50%;
            animation: fall linear infinite;
        }
        .snowflake:nth-child(1) { left: 10%; animation-duration: 5s; animation-delay: 0s; }
        .snowflake:nth-child(2) { left: 20%; animation-duration: 6s; animation-delay: 1s; }
        .snowflake:nth-child(3) { left: 30%; animation-duration: 4s; animation-delay: 2s; }
        .snowflake:nth-child(4) { left: 40%; animation-duration: 7s; animation-delay: 0.5s; }
        .snowflake:nth-child(5) { left: 50%; animation-duration: 5.5s; animation-delay: 1.5s; }
        .snowflake:nth-child(6) { left: 60%; animation-duration: 6.5s; animation-delay: 0.2s; }
        .snowflake:nth-child(7) { left: 70%; animation-duration: 4.5s; animation-delay: 1.8s; }
        .snowflake:nth-child(8) { left: 80%; animation-duration: 5.8s; animation-delay: 0.8s; }
        .snowflake:nth-child(9) { left: 90%; animation-duration: 6.2s; animation-delay: 1.2s; }
        .snowflake:nth-child(10) { left: 15%; animation-duration: 5.3s; animation-delay: 0.3s; }
        @keyframes fall {
            0% { transform: translateY(-10px); }
            100% { transform: translateY(100vh); }
        }
        .scene {
            position: relative;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .tree {
            position: relative;
            width: 200px;
            height: 300px;
            z-index: 2;
        }
        .trunk {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 20px;
            height: 50px;
            background: #8B4513;
            border-radius: 5px;
        }
        .layer {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 0;
            border-left: 50px solid transparent;
            border-right: 50px solid transparent;
            border-bottom: 80px solid #228B22;
        }
        .layer:nth-child(2) { bottom: 50px; }
        .layer:nth-child(3) { bottom: 130px; }
        .layer:nth-child(4) { bottom: 210px; }
        .star {
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 0;
            border-left: 15px solid transparent;
            border-right: 15px solid transparent;
            border-bottom: 25px solid #FFD700;
            animation: twinkle 1s infinite alternate;
        }
        .star::after {
            content: '';
            position: absolute;
            top: 10px;
            left: -15px;
            width: 0;
            height: 0;
            border-left: 15px solid transparent;
            border-right: 15px solid transparent;
            border-top: 25px solid #FFD700;
        }
        .lights {
            position: absolute;
            width: 100%;
            height: 100%;
        }
        .light {
            position: absolute;
            width: 8px;
            height: 8px;
            border-radius: 50%;
            animation: blink 2s infinite;
        }
        .light:nth-child(1) { background: #FF0000; top: 50px; left: 40%; animation-delay: 0s; }
        .light:nth-child(2) { background: #00FF00; top: 80px; left: 60%; animation-delay: 0.5s; }
        .light:nth-child(3) { background: #0000FF; top: 110px; left: 30%; animation-delay: 1s; }
        .light:nth-child(4) { background: #FFFF00; top: 140px; left: 70%; animation-delay: 1.5s; }
        .light:nth-child(5) { background: #FF00FF; top: 170px; left: 50%; animation-delay: 0.2s; }
        .light:nth-child(6) { background: #00FFFF; top: 200px; left: 35%; animation-delay: 0.7s; }
        .light:nth-child(7) { background: #FFA500; top: 230px; left: 65%; animation-delay: 1.2s; }
        .people {
            position: absolute;
            bottom: 20px;
            width: 100%;
            display: flex;
            justify-content: space-around;
            z-index: 1;
        }
        .person {
            width: 30px;
            height: 50px;
            animation: celebrate 2s infinite;
        }
        .person:nth-child(1) { animation-delay: 0s; }
        .person:nth-child(2) { animation-delay: 0.5s; }
        .person:nth-child(3) { animation-delay: 1s; }
        @keyframes celebrate {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0.3; }
        }
        @keyframes twinkle {
            0% { opacity: 1; }
            100% { opacity: 0.5; }
        }
    </style>
</head>
<body>
    <div class="floating-gifts">
        <div class="gift">🎁</div>
        <div class="gift">🎁</div>
        <div class="gift">🎁</div>
        <div class="gift">🎁</div>
        <div class="gift">🎁</div>
        <div class="gift">🎁</div>
        <div class="gift">🎁</div>
        <div class="gift">🎁</div>
    </div>
    <div class="snow">
        <div class="snowflake"></div>
        <div class="snowflake"></div>
        <div class="snowflake"></div>
        <div class="snowflake"></div>
        <div class="snowflake"></div>
        <div class="snowflake"></div>
        <div class="snowflake"></div>
        <div class="snowflake"></div>
        <div class="snowflake"></div>
        <div class="snowflake"></div>
    </div>
    <div class="scene">
        <div class="tree">
            <div class="star"></div>
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="trunk"></div>
            <div class="lights">
                <div class="light"></div>
                <div class="light"></div>
                <div class="light"></div>
                <div class="light"></div>
                <div class="light"></div>
                <div class="light"></div>
                <div class="light"></div>
            </div>
        </div>
        <div class="people">
            <div class="person">
                <svg width="30" height="50" viewBox="0 0 30 50">
                    <circle cx="15" cy="10" r="8" fill="black"/>
                    <rect x="10" y="18" width="10" height="15" fill="black"/>
                    <line x1="10" y1="25" x2="5" y2="35" stroke="black" stroke-width="2"/>
                    <line x1="20" y1="25" x2="25" y2="35" stroke="black" stroke-width="2"/>
                    <line x1="15" y1="33" x2="10" y2="45" stroke="black" stroke-width="2"/>
                    <line x1="15" y1="33" x2="20" y2="45" stroke="black" stroke-width="2"/>
                </svg>
            </div>
            <div class="person">
                <svg width="30" height="50" viewBox="0 0 30 50">
                    <circle cx="15" cy="10" r="8" fill="black"/>
                    <rect x="10" y="18" width="10" height="15" fill="black"/>
                    <line x1="10" y1="25" x2="5" y2="35" stroke="black" stroke-width="2"/>
                    <line x1="20" y1="25" x2="25" y2="35" stroke="black" stroke-width="2"/>
                    <line x1="15" y1="33" x2="10" y2="45" stroke="black" stroke-width="2"/>
                    <line x1="15" y1="33" x2="20" y2="45" stroke="black" stroke-width="2"/>
                </svg>
            </div>
            <div class="person">
                <svg width="30" height="50" viewBox="0 0 30 50">
                    <circle cx="15" cy="10" r="8" fill="black"/>
                    <rect x="10" y="18" width="10" height="15" fill="black"/>
                    <line x1="10" y1="25" x2="5" y2="35" stroke="black" stroke-width="2"/>
                    <line x1="20" y1="25" x2="25" y2="35" stroke="black" stroke-width="2"/>
                    <line x1="15" y1="33" x2="10" y2="45" stroke="black" stroke-width="2"/>
                    <line x1="15" y1="33" x2="20" y2="45" stroke="black" stroke-width="2"/>
                </svg>
            </div>
        </div>
    </div>
</body>
</html>
