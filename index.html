<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Worm.io Edukasi - Kuis Norma</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: #0f172a; /* slate-900 */
            touch-action: none; /* Prevent pull-to-refresh on mobile */
            font-family: 'Inter', sans-serif;
        }
        canvas {
            display: block;
            width: 100%;
            height: 100%;
        }
        
        /* Neon text effect */
        .neon-text {
            text-shadow: 0 0 10px rgba(52, 211, 153, 0.7), 0 0 20px rgba(52, 211, 153, 0.5), 0 0 30px rgba(16, 185, 129, 0.4);
        }

        /* Custom Scrollbar for Leaderboard */
        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: rgba(30, 41, 59, 0.5); 
            border-radius: 4px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: rgba(71, 85, 105, 0.8); 
            border-radius: 4px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover {
            background: rgba(100, 116, 139, 1); 
        }
    </style>
</head>
<body class="relative w-screen h-screen">

    <!-- Game Canvas -->
    <canvas id="gameCanvas" class="absolute inset-0 z-0"></canvas>

    <!-- UI Overlay -->
    <div id="ui-layer" class="absolute inset-0 flex flex-col justify-between pointer-events-none z-10">
        <!-- In-Game UI Elements -->
        <div class="absolute inset-0 pointer-events-none">
            <!-- Score (Bottom Left) -->
            <div id="score-display" class="hidden absolute bottom-6 left-4 md:bottom-8 md:left-8 flex-col items-start bg-slate-800/60 p-3 md:p-4 rounded-xl border border-slate-600 backdrop-blur-sm pointer-events-auto z-50 transition-all">
                <span class="text-xs md:text-sm text-slate-400 font-bold uppercase tracking-wider">Skor</span>
                <span class="text-2xl md:text-4xl font-extrabold text-white drop-shadow-lg" id="score">0</span>
            </div>
            
            <!-- Quiz Panel (Top Center) - DIPERKECIL -->
            <div id="quiz-panel" class="hidden flex-col items-center bg-slate-800/95 p-2 md:p-3 rounded-lg border border-slate-600 backdrop-blur-md w-[90%] md:w-full max-w-md mx-auto shadow-2xl absolute left-1/2 transform -translate-x-1/2 top-2 pointer-events-auto z-50 transition-all duration-300">
                <p id="quiz-question" class="text-[10px] md:text-sm text-emerald-300 font-semibold text-center mb-1 md:mb-1.5 px-1 leading-tight">Pertanyaan...</p>
                <div class="bg-slate-900/60 px-3 py-1 rounded-md border border-slate-700/50 mb-1.5 min-w-[120px] md:min-w-[160px] flex justify-center">
                    <p id="quiz-answer" class="text-base md:text-xl font-mono tracking-[0.2em] font-black text-white text-center">_ _ _ _</p>
                </div>
                <div id="quiz-target-indicator" class="transition-transform duration-200 ease-out text-[10px] md:text-xs text-yellow-400 font-bold bg-slate-900/90 px-3 py-1 rounded-full border border-yellow-500/40 shadow-[0_0_10px_rgba(234,179,8,0.25)] flex items-center gap-1.5">
                    <span>Cari huruf:</span> 
                    <span id="target-letter-display" class="text-sm md:text-base text-yellow-300 font-black">A</span>
                </div>
            </div>

            <!-- Minimap (Bottom Right) -->
            <div id="minimap-container" class="hidden absolute bottom-6 right-4 md:bottom-8 md:right-8 w-24 h-24 md:w-32 md:h-32 bg-slate-800/60 border border-slate-600 rounded-lg overflow-hidden backdrop-blur-sm pointer-events-auto z-50 transition-all">
                <!-- Simple dot representation for minimap -->
                <div id="minimap-player" class="absolute w-2 h-2 bg-emerald-400 rounded-full transform -translate-x-1/2 -translate-y-1/2 shadow-[0_0_5px_#34d399]"></div>
            </div>
        </div>

        <!-- Start / Game Over Screen -->
        <div id="menu-screen" class="absolute inset-0 flex flex-col md:flex-row items-center justify-center bg-slate-900/90 backdrop-blur-sm pointer-events-auto transition-opacity duration-300 z-50 overflow-y-auto pt-10 md:pt-0 gap-8">
            
            <!-- Left Side: Title and Controls -->
            <div class="flex flex-col items-center justify-center p-4 md:w-1/2 max-w-lg">
                <h1 class="text-6xl md:text-8xl font-black italic mb-2 text-transparent bg-clip-text bg-gradient-to-r from-green-400 to-emerald-600 neon-text pb-4">WORM.IO</h1>
                <p class="text-slate-300 mb-8 text-sm md:text-lg text-center px-4">Edukasi PKN (Norma): Arahkan cacing memakan huruf yang tepat. Lengkapi kata untuk menjawab pertanyaan!</p>
                
                <div id="game-over-stats" class="hidden flex-col items-center mb-6 p-6 bg-slate-800/80 rounded-2xl border border-slate-700 shadow-2xl w-full max-w-sm">
                    <span class="text-slate-400 font-semibold mb-1 uppercase tracking-widest">Skor Akhir</span>
                    <span class="text-5xl font-black text-white mb-6" id="final-score">0</span>
                    
                    <p id="save-status" class="text-sm text-emerald-400 text-center font-bold hidden bg-emerald-900/40 py-2 px-4 rounded-lg border border-emerald-500/30 w-full">✅ Skor otomatis tersimpan!</p>
                </div>

                <input type="text" id="main-player-name" maxlength="15" placeholder="Masukkan Nama Kamu..." class="mb-6 px-6 py-3 text-lg md:text-xl bg-slate-900/80 border-2 border-emerald-500/50 rounded-xl text-white text-center font-bold focus:outline-none focus:border-emerald-400 focus:ring-4 focus:ring-emerald-500/30 w-full max-w-xs shadow-[0_0_15px_rgba(16,185,129,0.2)] transition-all placeholder:text-slate-500">

                <button id="start-btn" class="px-10 py-4 bg-gradient-to-r from-emerald-500 to-green-600 hover:from-emerald-400 hover:to-green-500 text-white font-bold rounded-full text-xl shadow-[0_0_20px_rgba(16,185,129,0.5)] transform transition-transform hover:scale-105 active:scale-95 border-2 border-emerald-300/30 w-full max-w-xs">
                    Mulai Bermain
                </button>
            </div>

            <!-- Right Side: Leaderboard -->
            <div class="flex flex-col p-4 w-full md:w-1/3 max-w-sm bg-slate-800/60 rounded-2xl border border-slate-700 shadow-2xl max-h-[45vh] md:max-h-[70vh]">
                <h2 class="text-xl font-bold text-white mb-3 text-center border-b border-slate-600 pb-3 flex items-center justify-center gap-2">
                    <span>🏆</span> Top Global Peringkat
                </h2>
                <div id="leaderboard-list" class="flex flex-col gap-2 overflow-y-auto pr-2 custom-scrollbar">
                    <p class="text-slate-400 text-center text-sm italic py-4">Memuat data server...</p>
                </div>
            </div>
        </div>
    </div>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, doc, setDoc, getDoc, collection, onSnapshot } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // --- FIREBASE SETUP ---
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';
        
        let app, auth, db;
        let currentUser = null;

        try {
            // Wajib menggunakan sintaks yang tepat agar dikenali oleh environment (server)
            const firebaseConfig = JSON.parse(__firebase_config);
            
            app = initializeApp(firebaseConfig);
            auth = getAuth(app);
            db = getFirestore(app);
            console.log("Firebase berhasil diinisialisasi untuk Leaderboard.");
        } catch (e) {
            console.warn("Konfigurasi tidak terdeteksi. Bermain dalam mode Offline.", e);
            document.getElementById('leaderboard-list').innerHTML = '<p class="text-slate-400 text-center text-sm italic py-4">Mode Offline: Papan Peringkat sedang tidak tersedia.</p>';
        }

        async function initAuth() {
            if (!auth) return; // Lewati proses login jika sistem database tidak dimuat
            try {
                // Menggunakan Custom Token bawaan environment jika ada
                if (typeof __initial_auth_token !== 'undefined') {
                    await signInWithCustomToken(auth, __initial_auth_token);
                } else {
                    await signInAnonymously(auth);
                }
                
                currentUser = auth.currentUser;
                setupLeaderboardListener();
            } catch (error) {
                console.error("Auth error:", error);
                // Fallback ke anonim jika token custom gagal
                try {
                    await signInAnonymously(auth);
                    currentUser = auth.currentUser;
                    setupLeaderboardListener();
                } catch(e) {
                    console.error("Fallback auth error:", e);
                    document.getElementById('leaderboard-list').innerHTML = '<p class="text-red-400 text-center text-sm italic py-4">Gagal menghubungkan identitas pemain.</p>';
                }
            }
        }
        
        initAuth(); // Jalankan otentikasi segera

        function setupLeaderboardListener() {
            if (!currentUser || !db) return; // Aman dari error offline
            
            const lbRef = collection(db, 'artifacts', appId, 'public', 'data', 'leaderboard');
            
            onSnapshot(lbRef, (snapshot) => {
                let scores = [];
                snapshot.forEach(doc => {
                    scores.push({ id: doc.id, ...doc.data() });
                });
                
                // Urutkan skor secara descending (terbesar ke terkecil) dan ambil 10 teratas
                scores.sort((a, b) => b.score - a.score);
                const top10 = scores.slice(0, 10);
                renderLeaderboard(top10);
            }, (error) => {
                console.error("Error fetching leaderboard:", error);
                // Munculkan pesan error di panel sebelah kanan agar mudah dilacak
                document.getElementById('leaderboard-list').innerHTML = `<p class="text-red-400 text-center text-xs italic py-4">Gagal mengambil data: ${error.message}</p>`;
            });
        }

        function renderLeaderboard(scores) {
            const listEl = document.getElementById('leaderboard-list');
            listEl.innerHTML = '';
            
            if (scores.length === 0) {
                listEl.innerHTML = '<p class="text-slate-400 text-center text-sm italic py-4">Belum ada skor yang dicatat.</p>';
                return;
            }

            scores.forEach((entry, index) => {
                let rankStyle = "text-slate-400 font-bold";
                if (index === 0) rankStyle = "text-yellow-400 font-black drop-shadow-[0_0_5px_rgba(250,204,21,0.6)]";
                else if (index === 1) rankStyle = "text-slate-300 font-bold";
                else if (index === 2) rankStyle = "text-amber-600 font-bold";

                const isMe = currentUser && entry.id === currentUser.uid;
                const bgClass = isMe ? "bg-emerald-900/60 border-emerald-500/50" : "bg-slate-900/50 border-slate-700/50";

                const el = document.createElement('div');
                el.className = `flex justify-between items-center p-2.5 rounded-lg border ${bgClass}`;
                el.innerHTML = `
                    <div class="flex items-center gap-3 overflow-hidden">
                        <span class="text-sm md:text-base w-5 text-center ${rankStyle}">#${index + 1}</span>
                        <span class="font-medium text-white text-sm truncate max-w-[100px] md:max-w-[150px]">${entry.name || 'Anonim'}</span>
                        ${isMe ? '<span class="text-[9px] bg-emerald-500 text-white px-1.5 py-0.5 rounded-sm font-bold ml-1 tracking-wider uppercase">Kamu</span>' : ''}
                    </div>
                    <span class="font-mono font-black text-emerald-400">${entry.score}</span>
                `;
                listEl.appendChild(el);
            });
        }

        async function saveScoreToFirebase(playerName, score) {
            if (!currentUser || !db || score <= 0) return; // Aman dari error offline
            
            const finalName = playerName || 'Anonim';
            const userDocRef = doc(db, 'artifacts', appId, 'public', 'data', 'leaderboard', currentUser.uid);
            
            try {
                const docSnap = await getDoc(userDocRef);
                const existingScore = docSnap.exists() ? (docSnap.data().score || 0) : 0;
                
                // Hanya simpan dan timpa (merge) jika skor baru lebih tinggi (High Score)
                if (score > existingScore) {
                    await setDoc(userDocRef, { name: finalName, score: score, date: Date.now() }, { merge: true });
                }
            } catch(e) {
                console.error("Error saving score:", e);
                throw e; // Teruskan error agar terdeteksi UI (tombol hijau/merah)
            }
        }

        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const scoreElement = document.getElementById('score');
        const finalScoreElement = document.getElementById('final-score');
        const menuScreen = document.getElementById('menu-screen');
        const startBtn = document.getElementById('start-btn');
        const scoreDisplay = document.getElementById('score-display');
        const gameOverStats = document.getElementById('game-over-stats');
        const minimapContainer = document.getElementById('minimap-container');
        const minimapPlayer = document.getElementById('minimap-player');

        // Quiz DOM Elements
        const quizPanel = document.getElementById('quiz-panel');
        const quizQuestionEl = document.getElementById('quiz-question');
        const quizAnswerEl = document.getElementById('quiz-answer');
        const targetLetterDisplay = document.getElementById('target-letter-display');
        const quizTargetIndicator = document.getElementById('quiz-target-indicator');

        // Game Configuration
        const WORLD_SIZE = 4000;
        const FOOD_COUNT = 400;
        const GRID_SIZE = 50;
        
        // Quiz Data
        const quizData = [
            { q: "Norma yang bersumber dari hati nurani manusia adalah norma...", a: "KESUSILAAN" },
            { q: "Norma yang berisi petunjuk hidup dari Tuhan Yang Maha Esa adalah norma...", a: "AGAMA" },
            { q: "Norma yang bersumber dari pergaulan dan kebiasaan masyarakat adalah norma...", a: "KESOPANAN" },
            { q: "Norma yang dibuat oleh badan resmi negara dan bersifat memaksa adalah norma...", a: "HUKUM" },
            { q: "Sanksi berupa rasa menyesal mendalam biasanya dirasakan pelanggar norma...", a: "KESUSILAAN" },
            { q: "Sanksi penjara, denda, atau hukuman mati diberikan bagi pelanggar norma...", a: "HUKUM" },
            { q: "Sanksi bagi pelanggar norma agama diyakini berupa...", a: "DOSA" },
            { q: "Pelanggar norma kesopanan biasanya akan mendapat sanksi sosial yaitu...", a: "DIKUCILKAN" },
            { q: "Aturan atau ketentuan yang mengikat warga kelompok dalam masyarakat disebut...", a: "NORMA" },
            { q: "Dasar negara Indonesia yang menjadi sumber dari segala sumber hukum adalah...", a: "PANCASILA" },
            { q: "Sikap saling menghargai perbedaan antar sesama manusia disebut...", a: "TOLERANSI" },
            { q: "Hukuman atau balasan yang diberikan kepada pelanggar aturan disebut...", a: "SANKSI" },
            { q: "Sifat utama dari norma hukum adalah...", a: "MEMAKSA" },
            { q: "Membayar pajak tepat waktu adalah bentuk kepatuhan terhadap norma...", a: "HUKUM" },
            { q: "Mengucapkan permisi saat lewat di depan orang tua adalah contoh norma...", a: "KESOPANAN" },
            { q: "Tidak berbohong dan bersikap jujur merupakan penerapan norma...", a: "KESUSILAAN" },
            { q: "Menjalankan ibadah sesuai kepercayaan adalah wujud norma...", a: "AGAMA" },
            { q: "Sikap tidak memihak dan memberikan hak kepada yang berhak disebut...", a: "ADIL" },
            { q: "Kewajiban menaati rambu-rambu lalu lintas diatur dalam norma...", a: "HUKUM" },
            { q: "Tata krama dan etika berpakaian di tempat umum diatur oleh norma...", a: "KESOPANAN" },
            { q: "Tindakan mencuri atau merampok sangat bertentangan dengan norma...", a: "HUKUM" },
            { q: "Membantu nenek menyeberang jalan didorong oleh suara hati dari norma...", a: "KESUSILAAN" },
            { q: "Orang yang melanggar norma kesopanan biasanya akan mendapat teguran atau...", a: "DICELA" },
            { q: "Melanggar hukum di jalan raya akan ditindak oleh aparat yaitu...", a: "POLISI" },
            { q: "Norma kesusilaan berasal dari bisikan atau suara...", a: "NURANI" },
            { q: "Aturan tidak tertulis yang diakui dan dipatuhi oleh masyarakat lokal disebut...", a: "ADAT" },
            { q: "Hukum dasar negara kita yang tertulis adalah...", a: "UUD" },
            { q: "Norma hukum berlaku untuk seluruh warga negara tanpa terkecuali, bersifat...", a: "UMUM" },
            { q: "Tujuan utama dibuatnya norma dan hukum adalah menciptakan...", a: "KETERTIBAN" },
            { q: "Datang ke sekolah tepat waktu adalah bentuk sikap...", a: "DISIPLIN" },
            { q: "Membuang sampah pada tempatnya mencerminkan budaya dan norma...", a: "KESOPANAN" },
            { q: "Sila kedua Pancasila sangat berkaitan erat dengan penerapan norma...", a: "KESUSILAAN" },
            { q: "Tidak menyontek saat ulangan adalah contoh perilaku...", a: "JUJUR" },
            { q: "Hukum yang mengatur hubungan antar individu (seperti utang piutang) adalah hukum...", a: "PERDATA" },
            { q: "Hukum yang mengatur tentang kejahatan dan pelanggaran publik adalah hukum...", a: "PIDANA" },
            { q: "Sanksi rasa bersalah berasal dari dalam...", a: "DIRI" },
            { q: "Karena bersumber dari Tuhan, norma agama sering juga disebut norma...", a: "ILAHI" },
            { q: "Kebiasaan atau adat istiadat masyarakat yang turun-temurun disebut...", a: "TRADISI" },
            { q: "Hukum berfungsi melindungi masyarakat agar tercipta rasa...", a: "AMAN" },
            { q: "Lembaga resmi negara yang bertugas memutus perkara pelanggaran hukum adalah...", a: "PENGADILAN" },
            { q: "Sikap tenggang rasa dan bisa merasakan perasaan orang lain disebut...", a: "EMPATI" },
            { q: "Saling tolong menolong antar tetangga menciptakan suasana...", a: "KERUKUNAN" },
            { q: "Makan dan minum menggunakan tangan kanan sesuai dengan norma...", a: "KESOPANAN" },
            { q: "Berkhianat terhadap teman akan melukai hati nurani dan melanggar norma...", a: "KESUSILAAN" },
            { q: "Aturan hukum dibuat oleh lembaga resmi dari...", a: "NEGARA" },
            { q: "Berbuat baik tanpa mengharapkan imbalan disebut...", a: "IKHLAS" },
            { q: "Sanksi menggunjing atau cibiran dari tetangga terjadi bila melanggar norma...", a: "KESOPANAN" },
            { q: "Dalam hukum pidana, hukuman bagi pencuri yang paling umum adalah masuk...", a: "PENJARA" },
            { q: "Tidak merusak fasilitas umum adalah bentuk taat pada norma...", a: "HUKUM" },
            { q: "Musyawarah untuk mufakat adalah ciri khas penyelesaian masalah bangsa...", a: "INDONESIA" }
        ];
        
        let currentQuestionIndex = 0;
        let currentWordIndex = 0;
        let currentAnswer = "";
        let targetLetter = "";
        let playerName = "Anonim";

        // State
        let isPlaying = false;
        let animationId;
        
        // Input tracking
        let mouseX = 0;
        let mouseY = 0;
        
        // Camera logic
        let camera = {
            x: WORLD_SIZE / 2,
            y: WORLD_SIZE / 2,
            zoom: 1
        };

        // Utility: Random Range
        function randomRange(min, max) {
            return Math.random() * (max - min) + min;
        }

        // Quiz Logic Functions
        function loadNextQuestion() {
            currentQuestionIndex = (currentQuestionIndex + 1) % quizData.length;
            initQuizQuestion();
        }

        function initQuizQuestion() {
            currentWordIndex = 0;
            currentAnswer = quizData[currentQuestionIndex].a;
            targetLetter = currentAnswer[currentWordIndex];
            
            quizQuestionEl.innerText = quizData[currentQuestionIndex].q;
            updateQuizUI();
        }

        function updateQuizUI() {
            let displayStr = "";
            for (let i = 0; i < currentAnswer.length; i++) {
                if (i < currentWordIndex) {
                    displayStr += currentAnswer[i];
                } else {
                    displayStr += "_";
                }
            }
            quizAnswerEl.innerText = displayStr;
            
            if (targetLetter) {
                targetLetterDisplay.innerText = targetLetter;
                // Animate indicator pulse
                quizTargetIndicator.classList.add('scale-110', 'bg-yellow-800/80');
                setTimeout(() => quizTargetIndicator.classList.remove('scale-110', 'bg-yellow-800/80'), 250);
            }
        }

        function handleLetterCollected() {
            currentWordIndex++;
            playerWorm.targetLength += 3; // Cacing bertumbuh jika makan huruf yang benar
            playerWorm.applySpeedBuff(); // Memicu buff kecepatan 50%
            
            if (currentWordIndex >= currentAnswer.length) {
                // Jawaban berhasil diselesaikan
                playerWorm.score += 10; // Tambah 10 Poin
                playerWorm.addPermanentSpeedBuff(); // Buff kecepatan permanen 5%
                scoreElement.innerText = playerWorm.score;
                
                targetLetter = ""; // Jeda pencarian agar pemain tidak salah ambil
                updateQuizUI();
                quizTargetIndicator.style.display = 'none';
                
                // Visual Flash Hijau (selebrasi)
                quizPanel.classList.add('border-green-400', 'shadow-[0_0_40px_rgba(74,222,128,0.7)]');
                
                // Pindah ke pertanyaan berikutnya setelah jeda
                setTimeout(() => {
                    quizPanel.classList.remove('border-green-400', 'shadow-[0_0_40px_rgba(74,222,128,0.7)]');
                    quizTargetIndicator.style.display = 'flex';
                    loadNextQuestion();
                }, 2000);
            } else {
                targetLetter = currentAnswer[currentWordIndex];
                updateQuizUI();
            }
        }

        // Color Palette for Food
        const foodColors = ['#f87171', '#fbbf24', '#34d399', '#60a5fa', '#a78bfa', '#f472b6'];

        class Food {
            constructor() {
                this.respawn();
            }

            respawn() {
                // Keep food away from the extreme edges
                this.x = randomRange(100, WORLD_SIZE - 100);
                this.y = randomRange(100, WORLD_SIZE - 100);
                this.radius = randomRange(14, 18); // Diperbesar sedikit agar sesuai area sentuh huruf
                this.color = foodColors[Math.floor(Math.random() * foodColors.length)];
                this.pulse = Math.random() * Math.PI; // For glowing effect animation
                
                // 40% probabilitas memunculkan huruf target yang dibutuhkan saat ini
                if (typeof targetLetter !== 'undefined' && targetLetter && Math.random() < 0.40) {
                    this.letter = targetLetter;
                } else {
                    // Menghasilkan huruf acak dari A (kode ASCII 65) sampai Z (kode ASCII 90)
                    const charCode = Math.floor(randomRange(65, 91));
                    this.letter = String.fromCharCode(charCode);
                }
            }

            draw(ctx) {
                this.pulse += 0.05;
                const currentRadius = this.radius + Math.sin(this.pulse) * 2; // Pulsing effect

                ctx.save();
                
                // Draw glow
                ctx.shadowBlur = 15;
                ctx.shadowColor = this.color;
                
                // Set text properties
                ctx.font = `bold ${currentRadius * 1.5}px Inter, sans-serif`;
                ctx.fillStyle = this.color;
                ctx.textAlign = "center";
                ctx.textBaseline = "middle";
                
                // Draw the letter
                ctx.fillText(this.letter, this.x, this.y);
                
                ctx.restore();
            }
        }

        class Worm {
            constructor() {
                this.segments = [];
                const initialLength = 10;
                this.radius = 16;
                this.baseSpeed = 5;
                this.speed = this.baseSpeed;
                this.turnSpeed = 0.12;
                this.angle = 0;
                this.targetLength = initialLength;
                this.score = 0; // Mulai dari poin 0
                this.buffTimeout = null;
                this.isBuffed = false;

                // Initialize segments at center of world
                let startX = WORLD_SIZE / 2;
                let startY = WORLD_SIZE / 2;
                
                for (let i = 0; i < initialLength; i++) {
                    this.segments.push({ x: startX, y: startY });
                }
            }

            update(targetX, targetY) {
                let head = this.segments[0];
                
                // Calculate angle to target (mouse/touch relative to screen center)
                let dx = targetX - canvas.width / 2;
                let dy = targetY - canvas.height / 2;
                let targetAngle = Math.atan2(dy, dx);
                
                // Smoothly interpolate current angle towards target angle
                let angleDiff = targetAngle - this.angle;
                
                // Normalize angle difference to be between -PI and PI
                while (angleDiff > Math.PI) angleDiff -= Math.PI * 2;
                while (angleDiff < -Math.PI) angleDiff += Math.PI * 2;
                
                this.angle += angleDiff * this.turnSpeed;

                // Calculate new head position
                let newHead = {
                    x: head.x + Math.cos(this.angle) * this.speed,
                    y: head.y + Math.sin(this.angle) * this.speed
                };

                // World Bounds checking (Game Over condition)
                if (newHead.x < 0 || newHead.x > WORLD_SIZE || 
                    newHead.y < 0 || newHead.y > WORLD_SIZE) {
                    gameOver();
                    return;
                }

                // Add new head
                this.segments.unshift(newHead);

                // Check length and remove tail if not growing
                if (this.segments.length > this.targetLength) {
                    this.segments.pop();
                }
            }

            addPermanentSpeedBuff() {
                this.baseSpeed *= 1.05; // Meningkatkan kecepatan dasar sebesar 5%
                // Sesuaikan kecepatan saat ini (menyesuaikan apakah sedang ada buff 50% atau tidak)
                if (this.isBuffed) {
                    this.speed = this.baseSpeed * 1.5;
                } else {
                    this.speed = this.baseSpeed;
                }
            }

            applySpeedBuff() {
                this.isBuffed = true;
                this.speed = this.baseSpeed * 1.5; // Tambah kecepatan 50% dari base speed
                
                // Hapus timer lama jika buff tertumpuk (non-stackable kecepatan, tapi durasi reset)
                if (this.buffTimeout) {
                    clearTimeout(this.buffTimeout);
                }
                
                // Durasi buff: 3 detik (3000 ms)
                this.buffTimeout = setTimeout(() => {
                    this.speed = this.baseSpeed;
                    this.isBuffed = false;
                }, 3000);
            }

            draw(ctx) {
                // Draw body from tail to head
                for (let i = this.segments.length - 1; i >= 0; i--) {
                    let segment = this.segments[i];
                    
                    ctx.beginPath();
                    ctx.arc(segment.x, segment.y, this.radius, 0, Math.PI * 2);
                    
                    if (i === 0) {
                        // Head color
                        if (this.isBuffed) {
                            ctx.shadowBlur = 20;
                            ctx.shadowColor = '#fbbf24'; // Efek glow kuning di kepala saat buff aktif
                        }
                        ctx.fillStyle = '#10b981'; // emerald-500
                        ctx.fill();
                        ctx.shadowBlur = 0; // Reset shadow agar tidak tembus ke mata
                        
                        // Eyes
                        ctx.save();
                        ctx.translate(segment.x, segment.y);
                        ctx.rotate(this.angle);
                        
                        ctx.fillStyle = 'white';
                        ctx.beginPath(); ctx.arc(8, -6, 4, 0, Math.PI * 2); ctx.fill(); // Left eye
                        ctx.beginPath(); ctx.arc(8, 6, 4, 0, Math.PI * 2); ctx.fill();  // Right eye
                        
                        ctx.fillStyle = 'black';
                        ctx.beginPath(); ctx.arc(10, -6, 2, 0, Math.PI * 2); ctx.fill(); // Left pupil
                        ctx.beginPath(); ctx.arc(10, 6, 2, 0, Math.PI * 2); ctx.fill();  // Right pupil
                        
                        ctx.restore();

                    } else {
                        // Body gradient/pattern
                        let hue = 150 + (i * 2) % 40; // Variation of green
                        ctx.fillStyle = `hsl(${hue}, 80%, 50%)`;
                        ctx.fill();
                        
                        // Inner circle for detail
                        ctx.beginPath();
                        ctx.arc(segment.x, segment.y, this.radius * 0.6, 0, Math.PI * 2);
                        ctx.fillStyle = `hsl(${hue}, 80%, 40%)`;
                        ctx.fill();
                    }
                    
                    // Shadow for depth
                    ctx.shadowBlur = 10;
                    ctx.shadowColor = 'rgba(0,0,0,0.3)';
                }
                ctx.shadowBlur = 0; // Reset shadow
            }
        }

        // Game Entities
        let playerWorm;
        let foods = [];

        function initGame() {
            const nameInput = document.getElementById('main-player-name');
            playerName = nameInput.value.trim() || 'Anonim';
            localStorage.setItem('worm_player_name', playerName);

            currentQuestionIndex = 0;
            initQuizQuestion();

            playerWorm = new Worm();
            foods = [];
            for (let i = 0; i < FOOD_COUNT; i++) {
                foods.push(new Food());
            }
            
            scoreElement.innerText = playerWorm.score;
            
            // Initial camera position
            camera.x = playerWorm.segments[0].x;
            camera.y = playerWorm.segments[0].y;
            
            isPlaying = true;
            menuScreen.classList.add('hidden');
            scoreDisplay.classList.remove('hidden');
            minimapContainer.classList.remove('hidden');
            quizPanel.classList.remove('hidden');
            quizPanel.classList.add('flex');
            quizTargetIndicator.style.display = 'flex';
            
            // Center mouse logically
            mouseX = canvas.width / 2;
            mouseY = canvas.height / 2;

            if(animationId) cancelAnimationFrame(animationId);
            gameLoop();
        }

        function gameOver() {
            isPlaying = false;
            
            // Bersihkan timer buff jika game over saat buff masih jalan
            if (playerWorm && playerWorm.buffTimeout) {
                clearTimeout(playerWorm.buffTimeout);
            }
            
            finalScoreElement.innerText = playerWorm.score;
            
            menuScreen.classList.remove('hidden');
            scoreDisplay.classList.add('hidden');
            minimapContainer.classList.add('hidden');
            quizPanel.classList.add('hidden');
            quizPanel.classList.remove('flex');
            gameOverStats.classList.remove('hidden');
            gameOverStats.classList.add('flex');
            
            startBtn.innerText = "Main Lagi";

            // Tampilkan UI Simpan Skor jika poin pemain lebih dari 0
            const saveStatus = document.getElementById('save-status');

            if (playerWorm.score > 0 && currentUser) {
                saveStatus.classList.remove('hidden');
                saveStatus.innerText = "⏳ Menyimpan skor...";
                
                // Reset styling jika sebelumnya merah/hijau
                saveStatus.classList.remove('text-emerald-400', 'text-red-400', 'bg-emerald-900/40', 'bg-red-900/40', 'border-emerald-500/30', 'border-red-500/30');
                saveStatus.classList.add('text-yellow-400', 'bg-yellow-900/40', 'border-yellow-500/30');

                saveScoreToFirebase(playerName, playerWorm.score).then(() => {
                    saveStatus.innerText = "✅ Skor otomatis tersimpan!";
                    saveStatus.classList.replace('text-yellow-400', 'text-emerald-400');
                    saveStatus.classList.replace('bg-yellow-900/40', 'bg-emerald-900/40');
                    saveStatus.classList.replace('border-yellow-500/30', 'border-emerald-500/30');
                }).catch(e => {
                    saveStatus.innerText = "❌ Gagal menyimpan skor (Offline/Error).";
                    saveStatus.classList.replace('text-yellow-400', 'text-red-400');
                    saveStatus.classList.replace('bg-yellow-900/40', 'bg-red-900/40');
                    saveStatus.classList.replace('border-yellow-500/30', 'border-red-500/30');
                });
            } else {
                saveStatus.classList.add('hidden');
            }
        }

        function updateMinimap() {
            if(!isPlaying) return;
            let head = playerWorm.segments[0];
            
            // Calculate percentage position (0 to 1)
            let percentX = head.x / WORLD_SIZE;
            let percentY = head.y / WORLD_SIZE;
            
            // Minimap dimensions dynamically based on CSS size (w-24 or w-32)
            let mmWidth = minimapContainer.clientWidth;
            let mmHeight = minimapContainer.clientHeight;
            
            // Update UI dot
            minimapPlayer.style.left = `${percentX * mmWidth}px`;
            minimapPlayer.style.top = `${percentY * mmHeight}px`;
        }

        function update() {
            if (!isPlaying) return;

            // Update worm based on mouse/touch position
            playerWorm.update(mouseX, mouseY);
            
            // Smooth camera follow
            let head = playerWorm.segments[0];
            camera.x += (head.x - camera.x) * 0.1;
            camera.y += (head.y - camera.y) * 0.1;

            // Check if game over happened during update
            if(!isPlaying) return; 

            // Collision Detection with Food
            for (let i = 0; i < foods.length; i++) {
                let f = foods[i];
                let dx = head.x - f.x;
                let dy = head.y - f.y;
                let dist = Math.hypot(dx, dy);

                // Eat food
                if (dist < playerWorm.radius + f.radius) {
                    if (targetLetter && f.letter === targetLetter) {
                        handleLetterCollected();
                    }
                    
                    // Terlepas benar/salah, huruf yang dimakan akan hilang dan direset
                    // (Hanya huruf benar yang memicu pertumbuhan & poin)
                    f.respawn(); 
                }
            }

            updateMinimap();
        }

        function draw() {
            // Background
            ctx.fillStyle = '#1e293b'; // slate-800
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            if (!isPlaying) return;

            ctx.save();
            
            // Apply Camera Transform
            ctx.translate(canvas.width / 2, canvas.height / 2);
            ctx.scale(camera.zoom, camera.zoom);
            ctx.translate(-camera.x, -camera.y);

            // Draw Grid Lines (moving with world)
            ctx.strokeStyle = 'rgba(255, 255, 255, 0.05)';
            ctx.lineWidth = 2;
            
            // Optimize grid drawing based on camera view
            let startX = Math.floor((camera.x - canvas.width/(2*camera.zoom)) / GRID_SIZE) * GRID_SIZE;
            let endX = Math.ceil((camera.x + canvas.width/(2*camera.zoom)) / GRID_SIZE) * GRID_SIZE;
            let startY = Math.floor((camera.y - canvas.height/(2*camera.zoom)) / GRID_SIZE) * GRID_SIZE;
            let endY = Math.ceil((camera.y + canvas.height/(2*camera.zoom)) / GRID_SIZE) * GRID_SIZE;

            ctx.beginPath();
            for (let x = startX; x <= endX; x += GRID_SIZE) {
                if(x >= 0 && x <= WORLD_SIZE) {
                    ctx.moveTo(x, Math.max(0, startY));
                    ctx.lineTo(x, Math.min(WORLD_SIZE, endY));
                }
            }
            for (let y = startY; y <= endY; y += GRID_SIZE) {
                if(y >= 0 && y <= WORLD_SIZE) {
                    ctx.moveTo(Math.max(0, startX), y);
                    ctx.lineTo(Math.min(WORLD_SIZE, endX), y);
                }
            }
            ctx.stroke();

            // Draw World Boundaries (Red Danger Zone)
            ctx.strokeStyle = 'rgba(239, 68, 68, 0.8)'; // red-500
            ctx.lineWidth = 10;
            ctx.strokeRect(0, 0, WORLD_SIZE, WORLD_SIZE);
            // Inner danger glow
            ctx.strokeStyle = 'rgba(239, 68, 68, 0.3)';
            ctx.lineWidth = 30;
            ctx.strokeRect(-10, -10, WORLD_SIZE+20, WORLD_SIZE+20);

            // Draw Food
            for (let f of foods) {
                // Frustum culling (only draw if on screen)
                if (f.x > camera.x - canvas.width/(2*camera.zoom) - 50 &&
                    f.x < camera.x + canvas.width/(2*camera.zoom) + 50 &&
                    f.y > camera.y - canvas.height/(2*camera.zoom) - 50 &&
                    f.y < camera.y + canvas.height/(2*camera.zoom) + 50) {
                    f.draw(ctx);
                }
            }

            // Draw Player
            playerWorm.draw(ctx);

            ctx.restore();
        }

        function gameLoop() {
            update();
            draw();
            if (isPlaying) {
                animationId = requestAnimationFrame(gameLoop);
            }
        }

        // Event Listeners
        startBtn.addEventListener('click', initGame);

        // Memuat nama yang pernah disimpan sebelumnya (jika ada)
        const savedName = localStorage.getItem('worm_player_name');
        if (savedName) {
            document.getElementById('main-player-name').value = savedName;
        }

        function handlePointerMove(e) {
            if (!isPlaying) return;
            
            // Get pointer position relative to canvas
            const rect = canvas.getBoundingClientRect();
            
            if (e.touches && e.touches.length > 0) {
                mouseX = e.touches[0].clientX - rect.left;
                mouseY = e.touches[0].clientY - rect.top;
            } else {
                mouseX = e.clientX - rect.left;
                mouseY = e.clientY - rect.top;
            }
        }

        canvas.addEventListener('mousemove', handlePointerMove);
        canvas.addEventListener('touchmove', (e) => {
            e.preventDefault(); // Prevent scrolling on mobile while playing
            handlePointerMove(e);
        }, { passive: false });
        
        // Add touchstart for instant direction change upon tapping
        canvas.addEventListener('touchstart', (e) => {
            if (e.target === canvas) e.preventDefault();
            handlePointerMove(e);
        }, { passive: false });

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            
            // Adjust zoom based on screen size for mobile/tablet visibility
            if (window.innerWidth < 480) { // Layar HP Kecil
                camera.zoom = 0.55;
            } else if (window.innerWidth < 768) { // Tablet / HP Layar Lebar
                camera.zoom = 0.75; 
            } else { // Desktop
                camera.zoom = 1;
            }
        }

        window.addEventListener('resize', resizeCanvas);
        
        // Initial setup
        resizeCanvas();
    </script>
</body>
</html>
