# rhythmrush.github.io
rhythmrush.github.io
<!DOCTYPE html>
<html lang="ko"> 
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="icon" href="../2학기웹디/rhythmrush_logo.png"/> 
        <link rel="apple-touch-icon" href="../2학기웹디/rhythmrush_logo.png"/> 

    <title>Rhythm Rush</title>
    <style>
        
        body {
            font-family: Noto Sans KR, sans-serif;
            background-color: #FF66d8;
            color: #333;
            margin: 0;
            background-image: 
                radial-gradient(circle, rgb(255, 255, 255) 15%, transparent 16%),
                radial-gradient(circle, rgb(255, 255, 255) 15%, transparent 16%);
            background-size: 20px 20px;
            background-position: 0 0, 10px 10px;
            position: relative;
        }

        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(to bottom, rgba(255, 102, 216, 0.7), rgb(255, 255, 255));
            z-index: -1;
        }
        
        .particle {
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            width: 8px;
            height: 8px;
            background-color: #FF66D8;
            border-radius: 50%;
            mix-blend-mode: screen;
            filter: blur(1px);
            animation: particle-animation 1s ease-out forwards;
        }

        .particle:nth-of-type(3n) {
            background-color: #44ffb1;
            animation-duration: 1.2s;
        }
        .particle:nth-of-type(3n+1) {
            background-color: #fff154;
            animation-duration: 0.8s;
        }

        @keyframes particle-animation {
            0% {
                opacity: 1;
                transform: scale(1) translate(0, 0);
            }
            100% {
                opacity: 0;
                transform: scale(0) translate(var(--tx), var(--ty));
            }
        }

        @keyframes jello-horizontal {
            0% { transform: scale3d(1, 1, 1); }
            30% { transform: scale3d(1.25, 0.75, 1); }
            40% { transform: scale3d(0.75, 1.25, 1); }
            50% { transform: scale3d(1.15, 0.85, 1); }
            65% { transform: scale3d(0.95, 1.05, 1); }
            75% { transform: scale3d(1.05, 0.95, 1); }
            100% { transform: scale3d(1, 1, 1); }
        }

        .logo-section {
            padding: 1rem;
            text-align: center;
        }
        .logo {
            max-height: 100px;
        }
        .container {
            display: flex;
            height: 100vh;
        }
        .character-section {
            flex: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }
        .character-image {
            height: 85%;
            object-fit: contain;
            animation: float 3s ease-in-out infinite;
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        .content-section {
            flex: 2;
            padding: 2rem;
            overflow-y: auto;
        }
        h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            color: #FFE4F5;
        }
        .music-list {
            list-style-type: none;
            padding: 0;
        }
        .music-item {
            background: linear-gradient(to right, rgb(255, 205, 242) 0%, rgba(255, 205, 242, 0) 100%),
                url('../2학기웹디/rhythmrush_logo2.png') no-repeat left center;
                background-size: cover; 
            margin-bottom: 1rem;
            padding: 1rem;
            border-radius: 8px;
            transition: transform 0.3s ease;
            z-index: 1;
        }
        .music-item:hover {
            transform: scale(1.03);
            background: #ffcdf7;
            background: linear-gradient(to right, rgb(255, 205, 242) 0%, rgba(255, 205, 242, 0) 100%),
                url('../2학기웹디/rhythmrush_logo2hv.png') no-repeat left center;
                background-size: cover; 
        }
        .preview-button {
            background: none;
            border: none;
            color: #ff66d8;
            cursor: pointer;
            font-size: 1rem;
            margin-left: 0.5rem;
            transition: color 0.3s ease;
        }
        .preview-button:hover {
            color: #72ffc4;
        }
        .music-title {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            display: flex;
            align-items: center;
        }
        .music-artist {
            font-size: 0.9rem;
            color: #ffffff;
        }
        .difficulty {
            display: flex;
            margin-top: 0.5rem;
        }
        .difficulty span {
            width: 20px;
            height: 20px;
            background: #ffd700;
            margin-right: 5px;
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        }
    </style>
</head>
<body>
    <div class="logo-section">
        <img src="../2학기웹디/rhythmrush_logo.png" alt="로고" class="logo">
    </div>
    <div class="container">
        <div class="character-section">
            <img src="../2학기웹디/rhythmrush_chara.png" alt="게임 캐릭터" class="character-image">
        </div>
        <div class="content-section">
            <h1>MUSIC LIST</h1>
            <ul class="music-list">
                <li class="music-item"onclick="window.location.href='../2학기웹디/addiction_pattern.html'">
                    <div class="music-title">
                        ADDICT!ON
                        <button class="preview-button" onclick="event.stopPropagation(); previewSong('ADDICT!ON', this)">▶</button>
                    </div>
                    <div class="music-artist">아이리 칸나</div>
                    <div class="difficulty">
                        <span></span><span></span><span></span>
                    </div>
                    <audio id="ADDICT!ON" src="../2학기웹디/음원미리듣기/1_miri.mp3"></audio>
                </li>
                <li class="music-item"onclick="window.location.href='../2학기웹디/kidding_pattern.html'">
                    <div class="music-title">
                        KIDDING
                        <button class="preview-button" onclick="event.stopPropagation(); previewSong('KIDDING', this)">▶</button>
                    </div>
                    <div class="music-artist">이세계아이돌</div>
                    <div class="difficulty">
                        <span></span><span></span><span></span><span></span>
                    </div>
                    <audio id="KIDDING" src="../2학기웹디/음원미리듣기/2_miri.mp3"></audio>
                </li>
                <li class="music-item"onclick="window.location.href='../2학기웹디/fakeidol_pattern.html'">
                    <div class="music-title">
                        가짜 아이돌
                        <button class="preview-button" onclick="event.stopPropagation(); previewSong('가짜 아이돌', this)">▶</button>
                    </div>
                    <div class="music-artist">QWER</div>
                    <div class="difficulty">
                        <span></span><span></span>
                    </div>
                    <audio id="가짜 아이돌" src="../2학기웹디/음원미리듣기/3_miri.mp3"></audio>
                </li>
                <li class="music-item"onclick="window.location.href='../2학기웹디/nemo_pattern.html'">
                    <div class="music-title">
                        네모네모
                        <button class="preview-button" onclick="event.stopPropagation(); previewSong('네모네모', this)">▶</button>
                    </div>
                    <div class="music-artist">최예나</div>
                    <div class="difficulty">
                        <span></span><span></span><span></span><span></span><span></span>
                    </div>
                    <audio id="네모네모" src="../2학기웹디/음원미리듣기/4_miri.mp3"></audio>
                </li>
                <li class="music-item"onclick="window.location.href='../2학기웹디/milkyway_pattern.html'">
                    <div class="music-title">
                        Milky Way
                        <button class="preview-button" onclick="event.stopPropagation(); previewSong('Milky Way', this)">▶</button>
                    </div>
                    <div class="music-artist">StelLive</div>
                    <div class="difficulty">
                        <span></span><span></span><span></span><span></span>
                    </div>
                    <audio id="Milky Way" src="../2학기웹디/음원미리듣기/5_miri.mp3"></audio>
                </li>
                <li class="music-item"onclick="window.location.href='../2학기웹디/alone_pattern.html'">
                    <div class="music-title">
                        Alone
                        <button class="preview-button" onclick="event.stopPropagation(); previewSong('Alone', this)">▶</button>
                    </div>
                    <div class="music-artist">SeeU</div>
                    <div class="difficulty">
                        <span></span><span></span><span></span>
                    </div>
                    <audio id="Alone" src="../2학기웹디/음원미리듣기/6_miri.mp3"></audio>
                </li>
            </ul>
        </div>
    </div>

    <script>
          let currentlyPlaying = null;

        function previewSong(songTitle, button) {
            const audio = document.getElementById(songTitle);
            
            if (currentlyPlaying && currentlyPlaying !== audio) {
                currentlyPlaying.pause();
                currentlyPlaying.currentTime = 0;
                document.querySelector('.preview-button.playing').classList.remove('playing');
            }

            if (audio.paused) {
                audio.play();
                button.classList.add('playing');
                currentlyPlaying = audio;
            } else {
                audio.pause();
                audio.currentTime = 0;
                button.classList.remove('playing');
                currentlyPlaying = null;
            }
        }

        function createParticle(x, y) {
            const particle = document.createElement('div');
            particle.className = 'particle';

            const angle = Math.random() * Math.PI * 2;
            const distance = Math.random() * 100 + 50;
            const tx = Math.cos(angle) * distance;
            const ty = Math.sin(angle) * distance;

            particle.style.setProperty('--tx', `${tx}px`);
            particle.style.setProperty('--ty', `${ty}px`);

            particle.style.left = `${x}px`;
            particle.style.top = `${y}px`;

            document.body.appendChild(particle);

            particle.addEventListener('animationend', () => {
                particle.remove();
            });
        }

        let lastTime = 0;
        const PARTICLE_INTERVAL = 50;

        document.addEventListener('mousemove', (e) => {
            const currentTime = Date.now();
            if (currentTime - lastTime > PARTICLE_INTERVAL) {
                for (let i = 0; i < 3; i++) {
                    const offsetX = (Math.random() - 0.5) * 20;
                    const offsetY = (Math.random() - 0.5) * 20;
                    createParticle(e.clientX + offsetX, e.clientY + offsetY);
                }
                lastTime = currentTime;
            }
        });
    </script>
</body>
</html>
