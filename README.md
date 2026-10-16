
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#030711">
<title>VNX // CYBERSPACE</title>
<style>
:root {
  --cyan:#00eaff;
  --green:#39ffb0;
  --purple:#9b5cff;
  --bg:#030711;
  --panel:rgba(7,18,35,.78);
  --line:rgba(0,234,255,.25);
}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{
  margin:0;background:var(--bg);color:#e6f8ff;
  font-family:Consolas,"Courier New",monospace;
  overflow-x:hidden;
}
body:before{
  content:"";position:fixed;inset:0;pointer-events:none;z-index:-1;
  background:
    radial-gradient(ellipse at 20% 20%,#09244788,transparent 48%),
    radial-gradient(ellipse at 80% 60%,#16104466,transparent 50%),
    linear-gradient(#030711,#050b18);
}
#stars{position:fixed;inset:0;width:100%;height:100%;z-index:-1}
.scanlines{
  position:fixed;inset:0;pointer-events:none;z-index:20;opacity:.12;
  background:repeating-linear-gradient(0deg,transparent 0 3px,#6cfaff 4px,transparent 5px);
}
nav{
  position:sticky;top:0;z-index:10;display:flex;justify-content:space-between;
  align-items:center;gap:15px;padding:17px 5%;background:#030711d9;
  backdrop-filter:blur(15px);border-bottom:1px solid var(--line);
}
.logo{font-size:22px;font-weight:bold;color:var(--green);letter-spacing:5px}
nav a{color:#b8d9e7;text-decoration:none;font-size:12px;margin-left:20px}
nav a:hover{color:var(--cyan)}
.status{color:var(--green);font-size:10px;letter-spacing:2px}
main{width:min(1100px,92%);margin:auto}
.hero{
  min-height:78vh;display:flex;flex-direction:column;justify-content:center;
  align-items:center;text-align:center;position:relative;padding:65px 10px;
}
.eyebrow{color:var(--cyan);font-size:11px;letter-spacing:5px}
h1{
  font-size:clamp(55px,12vw,130px);margin:22px 0 8px;letter-spacing:10px;
  color:#fff;text-shadow:0 0 15px #00eaff99,0 0 55px #00eaff44;
}
.hero h2{font-size:clamp(13px,2vw,19px);color:var(--green);letter-spacing:4px}
.hero p{max-width:590px;color:#8faec3;line-height:1.9;font-size:13px}
.button{
  display:inline-block;padding:13px 22px;border:1px solid var(--cyan);
  color:var(--cyan);background:#00eaff0b;text-decoration:none;
  font:inherit;font-size:11px;letter-spacing:2px;cursor:pointer;
  transition:.2s;margin:8px;
}
.button:hover{background:var(--cyan);color:#031019;box-shadow:0 0 30px #00eaff55}
.blink{animation:blink 1.4s infinite}
@keyframes blink{50%{opacity:.35}}
.orbit{
  position:absolute;width:min(55vw,410px);aspect-ratio:1;border:1px solid #00eaff17;
  border-radius:50%;pointer-events:none;animation:rotate 28s linear infinite;
}
.orbit:before,.orbit:after{
  content:"";position:absolute;border:1px solid #39ffb020;border-radius:50%;
  inset:14%;
}
.orbit:after{inset:29%;border-color:#9b5cff28}
@keyframes rotate{to{transform:rotate(360deg)}}
section{padding:65px 0;scroll-margin-top:65px}
.section-label{font-size:11px;letter-spacing:4px;color:var(--cyan)}
h3{font-size:25px;letter-spacing:3px;margin:15px 0 28px}
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.panel{
  background:var(--panel);border:1px solid var(--line);padding:22px;
  position:relative;overflow:hidden;backdrop-filter:blur(12px);
}
.panel:before{
  content:"";position:absolute;top:0;left:0;width:60px;height:2px;
  background:var(--green);box-shadow:0 0 12px var(--green)
}
.panel h4{color:var(--green);font-size:13px;letter-spacing:2px}
.panel p{color:#90aabc;font-size:12px;line-height:1.9}
.tags{display:flex;gap:8px;flex-wrap:wrap}
.tag{border:1px solid #174b60;padding:8px 11px;color:#a9e7f3;font-size:11px}
.terminal{
  background:#02050b;border:1px solid #204b53;padding:20px;
  line-height:2;font-size:12px;overflow-wrap:anywhere;
}
.terminal .g{color:var(--green)}
.terminal .c{color:var(--cyan)}
/* GAME */
.game-shell{
  border:1px solid #00eaff66;background:#030712;
  box-shadow:0 0 40px #00eaff12;
}
.game-hud{
  display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap;
  padding:15px;background:#06101e;border-bottom:1px solid var(--line);
  font-size:11px;letter-spacing:1px;
}
.game-hud b{color:var(--green)}
#game{
  display:block;width:100%;height:auto;aspect-ratio:16/9;
  background:#030711;touch-action:none;cursor:crosshair;
}
.game-controls{
  display:flex;justify-content:center;align-items:center;flex-wrap:wrap;
  gap:8px;padding:15px;border-top:1px solid var(--line);
}
.game-note{text-align:center;color:#7794a8;font-size:11px;line-height:1.8;padding:0 15px 15px}
.mobile-controls{display:flex;gap:10px;justify-content:center;margin:10px}
.mobile-controls button{width:60px;height:45px;font-size:20px;touch-action:none}
footer{text-align:center;padding:45px 10px;border-top:1px solid var(--line);color:#658195;font-size:11px;line-height:2}
footer strong{color:var(--green)}
@media(max-width:700px){
 nav{padding:14px 4%}nav a{margin-left:9px;font-size:10px}
 .logo{font-size:17px;letter-spacing:3px}.status{display:none}
 .grid{grid-template-columns:1fr}
 .hero{min-height:70vh}h1{letter-spacing:4px}
 section{padding:45px 0}
}
</style>
</head>
<body>
<canvas id="stars"></canvas>
<div class="scanlines"></div>

<nav>
  <div class="logo">VNX<span style="color:white">.SYS</span></div>
  <div>
    <a href="#about">IDENTITY</a>
    <a href="#arsenal">ARSENAL</a>
    <a href="#game">GAME</a>
  </div>
  <div class="status"><span class="blink">●</span> ONLINE</div>
</nav>

<main>
  <header class="hero">
    <div class="orbit"></div>
    <div class="eyebrow">GALACTIC NETWORK // EST. VNX</div>
    <h1>VNX</h1>
    <h2>CYBERSECURITY RESEARCHER</h2>
    <p>
      Exploring the digital frontier. Researching vulnerabilities.
      Building tools. Defending systems. Welcome to my cyberspace.
    </p>
    <div style="margin-top:18px">
      <a class="button" href="#game">▶ LAUNCH SPACE DEFENSE</a>
      <a class="button" href="https://github.com/0V-N" target="_blank" rel="noopener">↗ ACCESS GITHUB</a>
    </div>
    <div class="eyebrow" style="margin-top:50px;font-size:9px">
      SYSTEM READY — SCROLL TO EXPLORE
    </div>
  </header>

  <section id="about">
    <div class="section-label">// 01 — OPERATOR IDENTITY</div>
    <h3>WHO AM I?</h3>
    <div class="grid">
      <div class="panel">
        <h4>◈ IDENTITY</h4>
        <p>Vishnu Narayanan<br>Also known as VN / VNX<br>Cybersecurity Researcher</p>
      </div>
      <div class="panel">
        <h4>◈ MISSION</h4>
        <p>Explore offensive security, discover weaknesses, develop practical security solutions, and build hands-on cyber labs.</p>
      </div>
      <div class="panel">
        <h4>◈ DIRECTIVE</h4>
        <p>Think like an attacker. Build like a developer. Defend like a professional.</p>
      </div>
    </div>
  </section>

  <section id="arsenal">
    <div class="section-label">// 02 — TECHNOLOGY MATRIX</div>
    <h3>THE ARSENAL</h3>
    <div class="panel">
      <h4>PROGRAMMING & DEVELOPMENT</h4>
      <div class="tags">
        <span class="tag">PYTHON</span><span class="tag">C / C++</span>
        <span class="tag">JAVASCRIPT</span><span class="tag">PHP</span>
        <span class="tag">HTML / CSS</span><span class="tag">BASH</span>
      </div>
      <h4 style="margin-top:28px">SECURITY & INFRASTRUCTURE</h4>
      <div class="tags">
        <span class="tag">KALI LINUX</span><span class="tag">NMAP</span>
        <span class="tag">NUCLEI</span><span class="tag">BURP SUITE</span>
        <span class="tag">METASPLOIT</span><span class="tag">OWASP</span>
        <span class="tag">DOCKER</span><span class="tag">SPLUNK</span>
        <span class="tag">GIT</span><span class="tag">LINUX</span>
      </div>
    </div>
  </section>

  <section id="projects">
    <div class="section-label">// 03 — RESEARCH DATABASE</div>
    <h3>MISSION ARCHIVE</h3>
    <div class="grid">
      <div class="panel">
        <h4>01 // SECURITY TOOLS</h4>
        <p>Python utilities, reconnaissance automation, and security testing experiments.</p>
        <a class="button" href="https://github.com/0V-N?tab=repositories">VIEW REPOS ↗</a>
      </div>
      <div class="panel">
        <h4>02 // CYBER LABS</h4>
        <p>Dockerized training environments, vulnerability labs, and reproducible experiments.</p>
        <a class="button" href="https://github.com/0V-N?tab=repositories">VIEW REPOS ↗</a>
      </div>
      <div class="panel">
        <h4>03 // CTF ENGINEERING</h4>
        <p>Hands-on security challenges and learning experiences for aspiring researchers.</p>
        <a class="button" href="https://github.com/0V-N?tab=repositories">VIEW REPOS ↗</a>
      </div>
    </div>
  </section>

  <section id="game">
    <div class="section-label">// 04 — INTERACTIVE CYBER RANGE</div>
    <h3>GALACTIC DEFENSE</h3>
    <p style="color:#8faec3;font-size:12px;line-height:2">
      Pilot your spacecraft. Destroy hostile drones. Survive as long as possible.
      Every wave increases the challenge.
    </p>
    <div class="game-shell">
      <div class="game-hud">
        <span>SCORE: <b id="score">000000</b></span>
        <span>HULL: <b id="hull">100%</b></span>
        <span>WAVE: <b id="wave">01</b></span>
        <span>STATUS: <b id="gameStatus">STANDBY</b></span>
      </div>
      <canvas id="game" width="960" height="540" aria-label="Playable space shooting game"></canvas>
      <div class="game-controls">
        <button class="button" id="start">▶ START MISSION</button>
        <button class="button" id="pause">Ⅱ PAUSE</button>
        <button class="button" id="restart">↻ RESTART</button>
      </div>
      <div class="mobile-controls">
        <button class="button" id="left" aria-label="Move left">←</button>
        <button class="button" id="fire" aria-label="Fire">◎</button>
        <button class="button" id="right" aria-label="Move right">→</button>
      </div>
      <div class="game-note">
        KEYBOARD: ← → or A / D to move · SPACE to fire · P to pause<br>
        MOBILE: Use the direction and fire controls below the game.<br>
        SIMULATION ONLY // No real systems are targeted.
      </div>
    </div>
  </section>

  <section id="terminal">
    <div class="section-label">// 05 — CONNECTION TERMINAL</div>
    <h3>ESTABLISH CONNECTION</h3>
    <div class="terminal">
      <div class="g">vnx@nexus:~$ whoami</div>
      <div class="c">Vishnu Narayanan // Cybersecurity Researcher</div>
      <div class="g">vnx@nexus:~$ connect --github</div>
      <div><a href="https://github.com/0V-N" style="color:#00eaff">github.com/0V-N ↗</a></div>
      <div class="g">vnx@nexus:~$ connect --instagram</div>
      <div><a href="https://instagram.com/vnx.py" style="color:#00eaff">instagram.com/vnx.py ↗</a></div>
      <div class="g">vnx@nexus:~$ connect --web</div>
      <div><a href="https://thevnx.com" style="color:#00eaff">thevnx.com ↗</a></div>
      <div class="g">vnx@nexus:~$ <span class="blink">█</span></div>
    </div>
  </section>
</main>

<footer>
  <strong>VNX // CYBERSPACE</strong><br>
  THINK BEYOND THE INTERFACE.<br>
  <span>BUILT FOR THE DIGITAL FRONTIER · © 2026 VNX</span>
</footer>

<script>
/* Background starfield */
const starCanvas = document.getElementById('stars');
const sx = starCanvas.getContext('2d');
let stars = [];
function resizeStars(){
  starCanvas.width = innerWidth * devicePixelRatio;
  starCanvas.height = innerHeight * devicePixelRatio;
  sx.setTransform(devicePixelRatio,0,0,devicePixelRatio,0,0);
  stars = Array.from({length:Math.min(220,Math.floor(innerWidth/5))},()=>({
    x:Math.random()*innerWidth,y:Math.random()*innerHeight,
    z:Math.random()*1.8+.2
  }));
}
function drawStars(){
  sx.clearRect(0,0,innerWidth,innerHeight);
  for(const s of stars){
    s.y += s.z*.24;
    if(s.y>innerHeight){s.y=0;s.x=Math.random()*innerWidth}
    sx.fillStyle=`rgba(120,225,255,${.25+s.z*.35})`;
    sx.fillRect(s.x,s.y,s.z,s.z);
  }
  requestAnimationFrame(drawStars);
}
addEventListener('resize',resizeStars);
resizeStars();drawStars();

/* GALACTIC DEFENSE — self-contained canvas game */
const canvas=document.getElementById('game');
const ctx=canvas.getContext('2d');
const $=id=>document.getElementById(id);
const W=960,H=540;
let running=false,over=false,score=0,hull=100,wave=1;
let ship,bullets,enemies,particles,gameStars,lastShot=0,spawnTimer=0;
const keys={};
let mobileLeft=false,mobileRight=false,mobileFire=false;
let lastTime=0,frameId=0;

function resetGame(){
  score=0;hull=100;wave=1;running=false;over=false;
  ship={x:W/2,y:H-65,r:17,speed:370,invuln:0};
  bullets=[];enemies=[];particles=[];spawnTimer=0;lastShot=0;
  gameStars=Array.from({length:90},()=>({
    x:Math.random()*W,y:Math.random()*H,s:Math.random()*2+.5,v:Math.random()*30+15
  }));
  updateHUD();drawGame();
}
function updateHUD(){
  $('score').textContent=String(score).padStart(6,'0');
  $('hull').textContent=Math.max(0,hull)+'%';
  $('wave').textContent=String(wave).padStart(2,'0');
  $('gameStatus').textContent=over?'MISSION FAILED':running?'ENGAGED':'STANDBY';
  $('gameStatus').style.color=over?'#ff5577':running?'#39ffb0':'#00eaff';
}
function fire(){
  if(!running||over)return;
  const now=performance.now();
  if(now-lastShot<170)return;
  lastShot=now;
  bullets.push({x:ship.x,y:ship.y-20,v:570,r:4});
  for(let i=0;i<2;i++)particles.push({
    x:ship.x+(Math.random()-.5)*9,y:ship.y-16,
    vx:(Math.random()-.5)*35,vy:60,life:.2,color='#00eaff'
  });
}
function spawnEnemy(){
  const elite=Math.random()<Math.min(.3,wave*.025);
  enemies.push({
    x:30+Math.random()*(W-60),y:-25,
    r:elite?20:14,health:elite?3:1,
    speed:(elite?65:90)+wave*8+Math.random()*30,
    phase:Math.random()*6.28,elite
  });
}
function explode(x,y,color,count=12){
  for(let i=0;i<count;i++){
    const a=Math.random()*Math.PI*2,v=Math.random()*160+25;
    particles.push({x,y,vx:Math.cos(a)*v,vy:Math.sin(a)*v,
      life:.25+Math.random()*.5,color});
  }
}
function drawShip(){
  ctx.save();ctx.translate(ship.x,ship.y);
  ctx.shadowBlur=18;ctx.shadowColor='#00eaff';
  ctx.fillStyle='#00eaff';ctx.strokeStyle='#baffff';ctx.lineWidth=2;
  ctx.beginPath();ctx.moveTo(0,-23);ctx.lineTo(17,15);
  ctx.lineTo(6,10);ctx.lineTo(0,15);ctx.lineTo(-6,10);
  ctx.lineTo(-17,15);ctx.closePath();ctx.fill();ctx.stroke();
  ctx.shadowBlur=10;ctx.fillStyle='#39ffb0';
  ctx.beginPath();ctx.moveTo(-5,17);ctx.lineTo(0,29+Math.random()*7);
  ctx.lineTo(5,17);ctx.fill();
  ctx.restore();
}
function drawEnemy(e){
  ctx.save();ctx.translate(e.x,e.y);
  ctx.rotate(Math.PI);
  ctx.strokeStyle=e.elite?'#bd5cff':'#ff5577';
  ctx.fillStyle=e.elite?'#431c69':'#47172b';
  ctx.lineWidth=2;ctx.shadowBlur=12;ctx.shadowColor=ctx.strokeStyle;
  ctx.beginPath();ctx.moveTo(0,-e.r);ctx.lineTo(e.r,0);
  ctx.lineTo(e.r*.5,e.r*.7);ctx.lineTo(0,e.r*.45);
  ctx.lineTo(-e.r*.5,e.r*.7);ctx.lineTo(-e.r,0);
  ctx.closePath();ctx.fill();ctx.stroke();
  ctx.restore();
}
function drawGame(){
  ctx.fillStyle='#030711';ctx.fillRect(0,0,W,H);
  const glow=ctx.createRadialGradient(W/2,H/2,10,W/2,H/2,500);
  glow.addColorStop(0,'#071c2d');glow.addColorStop(1,'#030711');
  ctx.fillStyle=glow;ctx.fillRect(0,0,W,H);
  ctx.strokeStyle='#00eaff0b';ctx.lineWidth=1;
  for(let x=0;x<W;x+=40){ctx.beginPath();ctx.moveTo(x,0);ctx.lineTo(x,H);ctx.stroke()}
  for(let y=0;y<H;y+=40){ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(W,y);ctx.stroke()}
  for(const s of gameStars||[]){
    ctx.fillStyle='#b8f5ff';ctx.globalAlpha=.3+s.s*.25;
    ctx.fillRect(s.x,s.y,s.s,s.s);
  }
  ctx.globalAlpha=1;
  for(const b of bullets){
    ctx.shadowBlur=15;ctx.shadowColor='#00eaff';
    ctx.fillStyle='#aaffff';ctx.fillRect(b.x-2,b.y-10,4,14);
  }
  ctx.shadowBlur=0;
  for(const e of enemies||[])drawEnemy(e);
  for(const p of particles||[]){
    ctx.globalAlpha=Math.max(0,p.life*2);
    ctx.fillStyle=p.color;ctx.fillRect(p.x,p.y,3,3);
  }
  ctx.globalAlpha=1;
  if(ship){
    if(ship.invuln<=0||Math.floor(performance.now()/100)%2===0)drawShip();
  }
  if(!running){
    ctx.textAlign='center';
    ctx.fillStyle='#00eaff';ctx.font='bold 25px monospace';
    ctx.shadowBlur=15;ctx.shadowColor='#00eaff';
    ctx.fillText(over?'SIGNAL LOST':'GALACTIC DEFENSE',W/2,H/2-15);
    ctx.shadowBlur=0;ctx.fillStyle='#a5c7d8';ctx.font='14px monospace';
    ctx.fillText(over?'Restart to launch another mission':'Press START MISSION to deploy',W/2,H/2+22);
    ctx.fillStyle='#39ffb0';ctx.font='12px monospace';
    ctx.fillText('MOVE  ◀ ▶     FIRE  SPACE     SURVIVE',W/2,H/2+53);
  }
  ctx.textAlign='left';
}
function step(t){
  frameId=requestAnimationFrame(step);
  const dt=Math.min((t-lastTime)/1000||0,.035);lastTime=t;
  if(!running){drawGame();return}
  for(const s of gameStars){s.y+=s.v*dt;if(s.y>H){s.y=0;s.x=Math.random()*W}}
  if(keys.ArrowLeft||keys.a||mobileLeft)ship.x-=ship.speed*dt;
  if(keys.ArrowRight||keys.d||mobileRight)ship.x+=ship.speed*dt;
  ship.x=Math.max(22,Math.min(W-22,ship.x));
  if(keys[' ']||mobileFire)fire();
  ship.invuln=Math.max(0,ship.invuln-dt);
  spawnTimer+=dt;
  if(spawnTimer>Math.max(.28,1.05-wave*.055)){spawnEnemy();spawnTimer=0}
  for(let i=bullets.length-1;i>=0;i--){
    const b=bullets[i];b.y-=b.v*dt;
    if(b.y< -20)bullets.splice(i,1);
  }
  for(let i=enemies.length-1;i>=0;i--){
    const e=enemies[i];e.y+=e.speed*dt;
    e.x+=Math.sin(t*.0015+e.phase)*45*dt;
    if(e.y>H+30){
      enemies.splice(i,1);hull=Math.max(0,hull-10);updateHUD();continue;
    }
    if(ship.invuln<=0&&Math.hypot(e.x-ship.x,e.y-ship.y)<e.r+14){
      enemies.splice(i,1);explode(e.x,e.y,'#ff5577');
      hull=Math.max(0,hull-20);ship.invuln=1;updateHUD();
      if(hull<=0){running=false;over=true;updateHUD()}
      continue;
    }
    for(let j=bullets.length-1;j>=0;j--){
      const b=bullets[j];
      if(Math.hypot(e.x-b.x,e.y-b.y)<e.r+5){
        bullets.splice(j,1);e.health--;
        if(e.health<=0){
          explode(e.x,e.y,e.elite?'#bd5cff':'#ff5577',18);
          enemies.splice(i,1);score+=e.elite?30:10;
          wave=1+Math.floor(score/150);updateHUD();
        }
        break;
      }
    }
  }
  for(let i=particles.length-1;i>=0;i--){
    const p=particles[i];p.x+=p.vx*dt;p.y+=p.vy*dt;p.life-=dt;
    if(p.life<=0)particles.splice(i,1);
  }
  drawGame();
}
$('start').onclick=()=>{if(over)resetGame();running=true;over=false;updateHUD()};
$('pause').onclick=()=>{running=!running&&!over;updateHUD()};
$('restart').onclick=()=>{resetGame();running=true;updateHUD()};
addEventListener('keydown',e=>{
  const k=e.key.length===1?e.key.toLowerCase():e.key;
  if(['ArrowLeft','ArrowRight',' '].includes(k))e.preventDefault();
  keys[k]=true;
  if(k==='p'&& !over){running=!running;updateHUD()}
});
addEventListener('keyup',e=>{
  const k=e.key.length===1?e.key.toLowerCase():e.key;
  keys[k]=false;
});
function hold(id,prop){
  const el=$(id);
  const on=e=>{e.preventDefault();window[prop]=true};
  const off=e=>{e.preventDefault();window[prop]=false};
  el.addEventListener('pointerdown',on);
  el.addEventListener('pointerup',off);
  el.addEventListener('pointercancel',off);
  el.addEventListener('pointerleave',off);
}
hold('left','mobileLeft');hold('right','mobileRight');hold('fire','mobileFire');
resetGame();
requestAnimationFrame(step);
</script>
</body>
</html>
