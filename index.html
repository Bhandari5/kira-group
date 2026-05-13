<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KeRa Rider - Infinite Knowledge</title>
    <style>
        /* All your existing styles remain exactly the same */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { background: #05050a; font-family: 'Segoe UI', sans-serif; color: #fff; overflow: hidden; }
        .screen { position: fixed; inset: 0; display: flex; align-items: center; justify-content: center; flex-direction: column; z-index: 10; }
        .screen.hidden { display: none !important; }
        #loginScreen { background: radial-gradient(circle, #1a1a2e 0%, #05050a 100%); }
        .box { background: rgba(255,255,255,0.03); border: 1px solid rgba(249,199,79,0.3); border-radius: 20px; padding: 40px; width: 380px; text-align: center; backdrop-filter: blur(10px); }
        h1 { font-size: 3rem; font-weight: 900; color: #f9c74f; letter-spacing: 5px; text-shadow: 0 0 20px rgba(249,199,79,0.5); margin-bottom: 20px; }
        input { width: 100%; padding: 12px; margin-bottom: 15px; background: rgba(0,0,0,0.5); border: 1px solid rgba(249,199,79,0.2); border-radius: 8px; color: #fff; outline: none; }
        .btn-primary { width: 100%; padding: 15px; background: #f9c74f; border: none; border-radius: 8px; color: #05050a; font-weight: 800; cursor: pointer; transition: 0.3s; }
        #hud { position: fixed; top: 0; left: 0; right: 0; padding: 20px; display: flex; align-items: center; gap: 30px; z-index: 5; background: linear-gradient(to bottom, rgba(0,0,0,0.8), transparent); }
        .hud-item { font-size: 1rem; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; }
        .hud-timer { color: #f9c74f; background: rgba(249,199,79,0.1); padding: 5px 15px; border-radius: 20px; border: 1px solid #f9c74f; }
        #quizPopup { position: fixed; inset: 0; background: rgba(0,0,0,0.9); display: flex; align-items: center; justify-content: center; z-index: 20; }
        .quiz-box { background: #0a0a1a; border: 3px solid #f9c74f; border-radius: 24px; padding: 40px; width: 90%; max-width: 450px; text-align: center; box-shadow: 0 0 50px rgba(249,199,79,0.2); }
        .quiz-opt { width: 100%; padding: 14px; margin: 8px 0; background: rgba(255,255,255,0.05); border: 1px solid rgba(249,199,79,0.3); color: #fff; cursor: pointer; border-radius: 10px; font-size: 1rem; transition: 0.2s; }
        .quiz-opt:hover { background: #f9c74f; color: #000; font-weight: 700; }
        canvas { display: block; }
    </style>
</head>
<body>

<div id="loginScreen" class="screen">
    <div class="box">
        <h1>KeRa</h1>
        <input type="text" id="userIn" placeholder="Enter Username">
        <input type="password" id="passIn" placeholder="Enter Password">
        <button class="btn-primary" onclick="handleAuth()">LAUNCH ENGINE</button>
    </div>
</div>

<div id="menuScreen" class="screen hidden">
    <h1>KeRa RIDER</h1>
    <p id="welcomeMsg" style="margin-bottom: 20px; color: #aaa;"></p>
    <button class="btn-primary" style="width:240px; margin-bottom:10px;" onclick="startGame()">▶ START RACE</button>
    <button onclick="location.reload()" style="background:none; border:none; color:#aaa; cursor:pointer; text-decoration:underline;">Logout</button>
</div>

<div id="hud" class="hidden">
    <div class="hud-item" style="color:#f9c74f">🪙 <span id="hCoins">0</span></div>
    <div class="hud-item" style="color:#ff6b6b">❤️ <span id="hLives">3</span></div>
    <div class="hud-item hud-timer">Quiz: <span id="hQuizTimer">15s</span></div>
    <div class="hud-item">Score: <span id="hScore">0</span></div>
</div>

<canvas id="gameCanvas"></canvas>

<div id="quizPopup" class="screen hidden">
    <div class="quiz-box">
        <h2 style="color:#f9c74f; margin-bottom:10px;">BRAIN POWER!</h2>
        <p id="qText" style="margin-bottom:25px; font-size: 1.3rem; font-weight: 500;"></p>
        <div id="qOpts"></div>
    </div>
</div>

<div id="gameOverScreen" class="screen hidden" style="background:rgba(0,0,0,0.95)">
    <h1 style="color:#ff6b6b">WRECKED</h1>
    <p id="finalStats" style="margin-bottom:30px; font-size:1.2rem;"></p>
    <button class="btn-primary" style="width:220px" onclick="startGame()">REDEPLOY</button>
</div>

<script>
/** ── 1. MASSIVE NON-REPEATING QUESTION POOL ── **/
const QUESTION_POOL = [
    // MATH
    { q: 'What is 5 + 7?', opts: ['10','11','12','13'], ans: 2 },
    { q: 'How many sides does a triangle have?', opts: ['2','3','4','5'], ans: 1 },
    { q: 'What is half of 20?', opts: ['5','10','15','20'], ans: 1 },
    { q: 'What is 10 x 3?', opts: ['13','20','30','40'], ans: 2 },
    { q: 'Which is bigger: 50 or 15?', opts: ['50','15','Both same','Neither'], ans: 0 },
    // ANIMALS
    { q: 'Which animal is the King of the Jungle?', opts: ['Tiger','Elephant','Lion','Grizzly'], ans: 2 },
    { q: 'How many legs does a spider have?', opts: ['6','8','10','12'], ans: 1 },
    { q: 'Which animal gives us milk?', opts: ['Dog','Cat','Cow','Lion'], ans: 2 },
    { q: 'What animal can fly?', opts: ['Elephant','Bird','Dog','Horse'], ans: 1 },
    { q: 'What do bees make?', opts: ['Milk','Honey','Juice','Sugar'], ans: 1 },
    { q: 'Which animal has a very long neck?', opts: ['Zebra','Elephant','Giraffe','Hippo'], ans: 2 },
    // SCIENCE & PLANETS
    { q: 'Which planet is the Red Planet?', opts: ['Mars','Jupiter','Venus','Saturn'], ans: 0 },
    { q: 'What do humans breathe to live?', opts: ['Water','Oxygen','Juice','Carbon'], ans: 1 },
    { q: 'Where does the Sun rise?', opts: ['North','South','East','West'], ans: 2 },
    { q: 'What color do you get if you mix Red and Blue?', opts: ['Green','Orange','Purple','Brown'], ans: 2 },
    { q: 'Is the Moon a star or a satellite?', opts: ['Star','Satellite','Planet','Sun'], ans: 1 },
    // GEOGRAPHY & GENERAL
    { q: 'How many days are in a week?', opts: ['5','6','7','8'], ans: 2 },
    { q: 'Which is the largest ocean?', opts: ['Atlantic','Indian','Arctic','Pacific'], ans: 3 },
    { q: 'What is the capital of the UK?', opts: ['Paris','New York','London','Tokyo'], ans: 2 },
    { q: 'What do you use to see things?', opts: ['Ears','Nose','Eyes','Hands'], ans: 2 },
    { q: 'Which season comes after Winter?', opts: ['Summer','Autumn','Spring','Rainy'], ans: 2 },
    { q: 'What is the frozen form of water called?', opts: ['Steam','Ice','Rain','Cloud'], ans: 1 }
];

let availableQuestions = [...QUESTION_POOL]; // This will track used questions

const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');
let W, H, animFrame, state;
let keys = {};

function resize() {
    W = canvas.width = window.innerWidth;
    H = canvas.height = window.innerHeight;
}
window.addEventListener('resize', resize);
resize();

function handleAuth() {
    const user = document.getElementById('userIn').value;
    if(user.length < 2) return alert("Enter a username!");
    document.getElementById('loginScreen').classList.add('hidden');
    document.getElementById('welcomeMsg').textContent = `Welcome, Rider ${user}!`;
    document.getElementById('menuScreen').classList.remove('hidden');
}

function initState() {
    let bg = [];
    for(let i=0; i<15; i++) {
        bg.push({
            x: Math.random() * W * 2,
            type: Math.random() > 0.5 ? 'tree' : 'building',
            w: 40 + Math.random() * 60,
            h: 100 + Math.random() * 200,
            speedMult: 0.3 + Math.random() * 0.2
        });
    }
    // Reset pool if empty
    if(availableQuestions.length === 0) availableQuestions = [...QUESTION_POOL];

    return {
        active: true, paused: false,
        bikeX: W * 0.2, bikeY: H * 0.7, bikeVY: 0,
        onGround: true,
        speed: 6, coins: 0, lives: 3, score: 0,
        quizTimer: 900,
        quizActive: false,
        obstacles: [],
        background: bg,
        roadY: H * 0.75
    };
}

function triggerQuiz() {
    state.quizActive = true;
    state.paused = true;

    // NO REPEAT LOGIC: Pick from available pool and remove it
    if(availableQuestions.length === 0) availableQuestions = [...QUESTION_POOL];
    const randomIndex = Math.floor(Math.random() * availableQuestions.length);
    const q = availableQuestions.splice(randomIndex, 1)[0];

    document.getElementById('qText').textContent = q.q;
    const optCont = document.getElementById('qOpts');
    optCont.innerHTML = '';
   
    q.opts.forEach((opt, i) => {
        const b = document.createElement('button');
        b.className = 'quiz-opt';
        b.textContent = opt;
        b.onclick = () => {
            if (i === q.ans) {
                state.score += 500;
                state.coins += 25;
            } else {
                state.lives--;
            }
            state.quizActive = false;
            state.paused = false;
            state.quizTimer = 900;
            document.getElementById('quizPopup').classList.add('hidden');
            if(state.lives <= 0) gameOver();
        };
        optCont.appendChild(b);
    });
    document.getElementById('quizPopup').classList.remove('hidden');
}

/** ── GAME LOOP LOGIC (Same as before) ── **/
function update() {
    if (!state.active || state.paused) return;
    if (keys['ArrowLeft'] || keys['KeyA']) state.bikeX -= 7;
    if (keys['ArrowRight'] || keys['KeyD']) state.bikeX += 7;
    if ((keys['Space'] || keys['ArrowUp']) && state.onGround) {
        state.bikeVY = -14;
        state.onGround = false;
    }
    if (!state.onGround) {
        state.bikeVY += 0.7;
        state.bikeY += state.bikeVY;
        if (state.bikeY >= state.roadY - 30) {
            state.bikeY = state.roadY - 30;
            state.onGround = true;
        }
    }
    state.quizTimer--;
    if (state.quizTimer <= 0) triggerQuiz();
    state.score += state.speed * 0.1;
    state.background.forEach(item => {
        item.x -= state.speed * item.speedMult;
        if(item.x + item.w < 0) item.x = W + Math.random() * 200;
    });
    if (state.quizTimer % 100 === 0) {
        state.obstacles.push({x: W + 100, y: state.roadY - 20});
    }
    state.obstacles.forEach((o, i) => {
        o.x -= state.speed;
        if (Math.abs(o.x - state.bikeX) < 18 && Math.abs(o.y - state.bikeY) < 18) {
            state.lives--;
            state.obstacles.splice(i, 1);
            if (state.lives <= 0) gameOver();
        }
    });
    state.obstacles = state.obstacles.filter(o => o.x > -100);
    updateHUD();
}

function draw() {
    ctx.fillStyle = '#05050a';
    ctx.fillRect(0, 0, W, H);
    state.background.forEach(item => {
        ctx.fillStyle = item.type === 'tree' ? '#0a1a0a' : '#0a0a1a';
        ctx.fillRect(item.x, state.roadY - item.h, item.w, item.h);
    });
    ctx.fillStyle = '#111';
    ctx.fillRect(0, state.roadY, W, H - state.roadY);
    ctx.fillStyle = '#f9c74f';
    ctx.fillRect(0, state.roadY, W, 4);

    state.obstacles.forEach(o => {
        const grad = ctx.createRadialGradient(o.x-5, o.y-5, 2, o.x, o.y, 20);
        grad.addColorStop(0, '#fff3b0'); grad.addColorStop(0.5, '#f9c74f'); grad.addColorStop(1, '#9a7805');
        ctx.fillStyle = grad;
        ctx.beginPath(); ctx.arc(o.x, o.y, 20, 0, Math.PI*2); ctx.fill();
    });

    ctx.save();
    ctx.translate(state.bikeX, state.bikeY);
    ctx.fillStyle = '#f9c74f';
    ctx.beginPath(); ctx.roundRect(-30, -15, 60, 25, 10); ctx.fill();
    ctx.fillStyle = '#000'; ctx.font = 'bold 14px Arial'; ctx.fillText('KeRa', -18, 4);
    ctx.fillStyle = '#222'; ctx.strokeStyle = '#f9c74f'; ctx.lineWidth = 3;
    ctx.beginPath(); ctx.arc(-22, 18, 14, 0, Math.PI*2); ctx.fill(); ctx.stroke();
    ctx.beginPath(); ctx.arc(22, 18, 14, 0, Math.PI*2); ctx.fill(); ctx.stroke();
    ctx.restore();
}

function updateHUD() {
    document.getElementById('hCoins').textContent = state.coins;
    document.getElementById('hLives').textContent = state.lives;
    document.getElementById('hScore').textContent = Math.floor(state.score);
    document.getElementById('hQuizTimer').textContent = Math.ceil(state.quizTimer / 60) + 's';
}

function loop() {
    update(); draw();
    if(state.active) animFrame = requestAnimationFrame(loop);
}

function startGame() {
    state = initState();
    document.getElementById('menuScreen').classList.add('hidden');
    document.getElementById('gameOverScreen').classList.add('hidden');
    document.getElementById('hud').classList.remove('hidden');
    loop();
}

function gameOver() {
    state.active = false;
    document.getElementById('gameOverScreen').classList.remove('hidden');
    document.getElementById('finalStats').textContent = `FINAL SCORE: ${Math.floor(state.score)} | COINS: ${state.coins}`;
}

window.addEventListener('keydown', e => keys[e.code] = true);
window.addEventListener('keyup', e => keys[e.code] = false);
</script>
</body>
</html>
