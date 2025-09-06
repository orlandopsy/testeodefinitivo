/* =========================
   Datos: 40 preguntas (20 CG + 20 Sistemas)
   ========================= */
const QUESTIONS = [
  // Cultura general
  { q: "¿Capital de Francia?", a: ["París","Lyon","Marsella","Niza"], correct: 0 },
  { q: "¿Río más largo del mundo?", a: ["Nilo","Yangtsé","Amazonas","Misisipi"], correct: 2 },
  { q: "¿Quién pintó la Mona Lisa?", a: ["Van Gogh","Leonardo da Vinci","Picasso","Miguel Ángel"], correct: 1 },
  { q: "¿Año de llegada a la Luna?", a: ["1965","1969","1971","1973"], correct: 1 },
  { q: "¿País con más habitantes?", a: ["India","China","EE. UU.","Indonesia"], correct: 0 },
  { q: "¿Elemento químico 'O'?", a: ["Oro","Osmio","Oxígeno","Oganesón"], correct: 2 },
  { q: "¿Océano más grande?", a: ["Atlántico","Índico","Pacífico","Ártico"], correct: 2 },
  { q: "¿Autor de 'Cien años de soledad'?", a: ["Borges","García Márquez","Cortázar","Vargas Llosa"], correct: 1 },
  { q: "¿País de las pirámides de Giza?", a: ["México","Egipto","Perú","Irán"], correct: 1 },
  { q: "¿Lengua más hablada como lengua materna?", a: ["Inglés","Hindi","Mandarín","Español"], correct: 2 },
  { q: "¿Quién formuló la teoría de la relatividad?", a: ["Einstein","Newton","Tesla","Planck"], correct: 0 },
  { q: "¿En qué continente está Nigeria?", a: ["Asia","África","América","Europa"], correct: 1 },
  { q: "¿País con forma de bota?", a: ["España","Italia","Grecia","Portugal"], correct: 1 },
  { q: "¿Cuántos planetas hay en el sistema solar?", a: ["7","8","9","10"], correct: 1 },
  { q: "¿Dónde se originaron los Juegos Olímpicos?", a: ["Roma","Grecia","Egipto","Francia"], correct: 1 },
  { q: "¿En qué país se encuentra Machu Picchu?", a: ["México","Chile","Perú","Bolivia"], correct: 2 },
  { q: "¿Cuál es el animal terrestre más rápido?", a: ["León","Tigre","Guepardo","Caballo"], correct: 2 },
  { q: "¿Qué gas respiramos principalmente?", a: ["Oxígeno","Nitrógeno","Dióxido de carbono","Hidrógeno"], correct: 1 },
  { q: "¿Qué moneda se usa en Japón?", a: ["Yen","Won","Yuan","Dólar"], correct: 0 },
  { q: "¿Cuál es el desierto más grande del mundo?", a: ["Kalahari","Sahara","Atacama","Gobi"], correct: 1 },

  // Sistemas / informática
  { q: "¿Qué significa HTML?", a: ["Hyperlink Text Maker","HyperText Markup Language","High Transfer Markup Language","Hyper Tool Multi Language"], correct: 1 },
  { q: "¿Qué significa CSS?", a: ["Creative Style System","Cascade Style Source","Cascading Style Sheets","Coding Style Sheets"], correct: 2 },
  { q: "¿Lenguaje que corre en el navegador?", a: ["Java","Python","JavaScript","C++"], correct: 2 },
  { q: "¿Qué es la CPU?", a: ["Unidad Central de Procesamiento","Memoria principal","Disco duro","Tarjeta de video"], correct: 0 },
  { q: "¿Qué es RAM?", a: ["Memoria de solo lectura","Memoria de acceso aleatorio","Memoria externa","Memoria de video"], correct: 1 },
  { q: "Comando para ver directorios en Linux", a: ["cd","rm","ls","mv"], correct: 2 },
  { q: "¿Protocolo para páginas web?", a: ["FTP","SMTP","HTTP","SSH"], correct: 2 },
  { q: "¿Qué es un algoritmo?", a: ["Un lenguaje","Un error","Conjunto de pasos para resolver un problema","Una base de datos"], correct: 2 },
  { q: "¿Qué base numérica usa una computadora?", a: ["Decimal","Octal","Binaria","Hexagesimal"], correct: 2 },
  { q: "SQL se usa para…", a: ["Redes","Sistemas operativos","Bases de datos","Diseño gráfico"], correct: 2 },
  { q: "¿Qué significa IP?", a: ["Internet Protocol","Internal Program","Instant Process","Input Port"], correct: 0 },
  { q: "¿Sistema operativo de código abierto más usado?", a: ["Linux","Windows","MacOS","Android"], correct: 0 },
  { q: "¿Qué significa WWW?", a: ["World Wide Web","Wide World Web","Web World Wide","Wide Web World"], correct: 0 },
  { q: "¿Qué extensión tienen los archivos de JavaScript?", a: [".java",".js",".jsx",".jsc"], correct: 1 },
  { q: "¿Qué significa URL?", a: ["Universal Resource Locator","Uniform Resource Locator","Unique Resource Link","Unified Routing Line"], correct: 1 },
  { q: "¿Qué es un bit?", a: ["Unidad mínima de información","Un byte","Un error","Un programa"], correct: 0 },
  { q: "¿Qué significa SO en informática?", a: ["Sistema Operativo","Servidor Online","Servicio Oficial","Software Opcional"], correct: 0 },
  { q: "¿Qué es un compilador?", a: ["Traductor de código fuente a máquina","Un lenguaje de programación","Un sistema operativo","Un editor de texto"], correct: 0 },
  { q: "¿Qué significa DNS?", a: ["Domain Name System","Data Network Service","Digital Number System","Device Name Source"], correct: 0 },
  { q: "¿Qué lenguaje se usa para consultas en bases de datos?", a: ["SQL","Python","HTML","C"], correct: 0 }
];

/* =========================
   Estado
   ========================= */
let username = null;
let score = 0;
let remaining = [];
let current = null;
let spinning = false;

/* =========================
   Selectores
   ========================= */
const $ = sel => document.querySelector(sel);
const startSec = $('#start');
const gameMain = $('#game');
const winSec = $('#win');

const hudUser = $('#hudUser');
const hudScore = $('#hudScore');
const wheelImg = $('#wheel');
const btnSpin = $('#btnSpin');

const qSection = $('#qa');
const qText = $('#qText');
const answersForm = $('#answers');
const btnSubmit = $('#btnSubmit');
const btnNext = $('#btnNext');
const feedback = $('#feedback');

const rankList = $('#ranking');

/* =========================
   Inicio / Pantalla
   ========================= */
$('#btnStart').addEventListener('click', () => {
  const val = $('#username').value.trim();
  if (!val) { alert('Escribe tu usuario'); return; }
  username = val;
  startSec.classList.add('hidden');
  gameMain.classList.remove('hidden');
  hudUser.textContent = username;
  score = 0;
  hudScore.textContent = score;

  // 🔹 Elegir 10 preguntas al azar del banco completo
  remaining = shuffle([...QUESTIONS]).slice(0, 10);

  updateRanking(); // pinta ranking actual
});

/* =========================
   Girar ruleta con SONIDO (Web Audio)
   ========================= */
btnSpin.addEventListener('click', () => spinWheel());

function spinWheel(){
  if(spinning) return;
  spinning = true;
  qSection.classList.add('hidden');
  feedback.textContent = '';
  btnSpin.disabled = true;

  const totalSegments = 12;            
  const segmentAngle = 360 / totalSegments;
  const finalAngle = 1440 + Math.random() * 1080; 
  const duration = 3500;               
  const start = performance.now();

  let lastTickIndex = -1;

  function frame(now){
    const t = Math.min(1, (now - start)/duration);
    const eased = 1 - Math.pow(1 - t, 3);
    const angle = eased * finalAngle;
    wheelImg.style.transform = `rotate(${angle}deg)`;

    const idx = Math.floor(((angle % 360)+0.0001) / segmentAngle);
    if(idx !== lastTickIndex){
      playTick();
      lastTickIndex = idx;
    }

    if(t < 1){
      requestAnimationFrame(frame);
    }else{
      spinning = false;
      btnSpin.disabled = false;
      showQuestion();
    }
  }
  requestAnimationFrame(frame);
}

const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
function playTick(){
  const o = audioCtx.createOscillator();
  const g = audioCtx.createGain();
  o.type = 'square';
  o.frequency.value = 900 + Math.random()*200;
  g.gain.value = 0.12;
  o.connect(g); g.connect(audioCtx.destination);
  o.start();
  g.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + 0.06);
  o.stop(audioCtx.currentTime + 0.07);
}

/* =========================
   Preguntas y respuestas
   ========================= */
function showQuestion(){
  if(remaining.length === 0){
    winGame();
    return;
  }
  current = remaining.pop(); 
  qText.textContent = current.q;
  answersForm.innerHTML = '';
  const letters = ['A','B','C','D'];
  current.a.forEach((opt, i) => {
    const id = `opt_${Date.now()}_${i}`;
    const row = document.createElement('label');
    row.innerHTML = `
      <input type="radio" name="ans" id="${id}" value="${i}">
      <span><strong>${letters[i]}.</strong> ${opt}</span>
    `;
    answersForm.appendChild(row);
  });
  btnSubmit.classList.remove('hidden');
  btnNext.classList.add('hidden');
  qSection.classList.remove('hidden');
}

btnSubmit.addEventListener('click', () => {
  const sel = answersForm.querySelector('input[name="ans"]:checked');
  if(!sel){ alert('Selecciona una opción'); return; }
  const val = +sel.value;
  const isCorrect = val === current.correct;
  if(isCorrect){
    score += 10;
    feedback.textContent = '✅ ¡Correcto!';
  }else{
    feedback.textContent = `❌ Incorrecto. Respuesta correcta: ${'ABCD'[current.correct]}`;
  }
  hudScore.textContent = score;
  saveScore();
  btnSubmit.classList.add('hidden');
  btnNext.classList.remove('hidden');
});

btnNext.addEventListener('click', () => {
  qSection.classList.add('hidden');
});

/* =========================
   Ranking (localStorage)
   ========================= */
function loadRanking(){
  try { return JSON.parse(localStorage.getItem('ruleta_ranking')||'[]'); }
  catch{ return []; }
}
function saveRanking(list){
  localStorage.setItem('ruleta_ranking', JSON.stringify(list));
}
function saveScore(){
  const list = loadRanking();
  const i = list.findIndex(x => x.user === username);
  if(i>=0){ list[i].score = Math.max(list[i].score, score); }
  else{ list.push({user: username, score}); }
  list.sort((a,b)=>b.score-a.score);
  saveRanking(list);
  updateRanking();
}
function updateRanking(){
  const list = loadRanking().slice(0,10);
  rankList.innerHTML = '';
  list.forEach((r,i)=>{
    const li = document.createElement('li');
    li.textContent = `${i+1}. ${r.user} — ${r.score} pts`;
    rankList.appendChild(li);
  });
}

/* =========================
   Victoria + confeti
   ========================= */
function winGame(){
  gameMain.classList.add('hidden');
  winSec.classList.remove('hidden');
  $('#winUser').textContent = username;
  $('#winScore').textContent = score;
  confettiBurst();
}
$('#btnRestart').addEventListener('click', ()=>{
  winSec.classList.add('hidden');
  startSec.classList.remove('hidden');
});

function confettiBurst(){
  const canvas = $('#confetti');
  const ctx = canvas.getContext('2d');
  const W = canvas.width = innerWidth;
  const H = canvas.height = innerHeight;
  const parts = Array.from({length: 150}).map(()=>({
    x: Math.random()*W, y: -20 - Math.random()*H/2,
    vx: (Math.random()*2-1)*2,
    vy: 2+Math.random()*3,
    size: 4+Math.random()*6,
    color: `hsl(${Math.random()*360},100%,60%)`,
    rot: Math.random()*Math.PI, vr: (Math.random()*2-1)*0.2
  }));
  let t=0;
  function loop(){
    ctx.clearRect(0,0,W,H);
    parts.forEach(p=>{
      p.x+=p.vx; p.y+=p.vy; p.rot+=p.vr;
      ctx.save();
      ctx.translate(p.x,p.y);
      ctx.rotate(p.rot);
      ctx.fillStyle=p.color;
      ctx.fillRect(-p.size/2,-p.size/2,p.size,p.size);
      ctx.restore();
    });
    t++;
    if(t<300) requestAnimationFrame(loop);
  }
  loop();
}

/* =========================
   Utilidad: mezclar array
   ========================= */
function shuffle(arr){
  for(let i=arr.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [arr[i],arr[j]]=[arr[j],arr[i]];
  }
  return arr;
}
