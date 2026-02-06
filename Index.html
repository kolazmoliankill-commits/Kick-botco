<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<title>Galaxia del Amor - Leslie</title>
<style>
    body,html{margin:0;height:100%;background:#000;overflow:hidden}
    canvas{display:block}
    .player{position:fixed;bottom:20px;left:50%;transform:translateX(-50%);width:90%;max-width:600px;display:flex;align-items:center;gap:10px;padding:10px;border:2px solid #f60;border-radius:999px;background:0 0;box-shadow:0 0 15px #f60,0 0 30px #f30;z-index:1000;font-family:Arial,sans-serif;color:#fff;font-size:14px}
    .player button{background:0 0;border:none;color:#fff;font-size:22px;cursor:pointer;filter:drop-shadow(0 0 6px #ff6600);transition:transform .2s}
    .player button:hover{transform:scale(1.2);filter:drop-shadow(0 0 10px #ff3300)}
    .progress{flex-grow:1;height:14px;background:rgba(255,255,255,.12);border-radius:999px;overflow:hidden;cursor:pointer;position:relative}
    .progress-bar{height:100%;width:0%;background:linear-gradient(270deg,#f60,#f30,#f09,#f60);background-size:400% 400%;border-radius:999px;box-shadow:0 0 10px #f60;animation:flowing 6s ease infinite}
    @keyframes flowing{0%{background-position:0 50%}50%{background-position:100% 50%}100%{background-position:0 50%}}
    .time{min-width:74px;text-align:right;font-size:12px;color:#fff;text-shadow:0 0 5px #f60}
</style>
</head>
<body>
<canvas id="c"></canvas>
<div class="player">
    <button id="play">▶️</button>
    <div class="progress" id="progress"><div class="progress-bar" id="progress-bar"></div></div>
    <div class="time" id="time">0:00 / 0:00</div>
</div>
<audio id="audio" loop>
    <source src="https://www.dropbox.com/scl/fi/qfv28rqu6b36jwusao4x4/Love.MP3?rlkey=ptjd053374f028aa4jfcfrfxn&st=1j0j51eo&raw=1" type="audio/mpeg">
</audio>

<script src="https://cdn.jsdelivr.net/npm/three@0.148.0/build/three.min.js"></script>
<script>
const audio=document.getElementById("audio"),playBtn=document.getElementById("play"),progress=document.getElementById("progress"),progressBar=document.getElementById("progress-bar"),timeDisplay=document.getElementById("time");
let isPlaying=!1;
function formatTime(e){if(!isFinite(e))return"0:00";return Math.floor(e/60)+":"+Math.floor(e%60).toString().padStart(2,"0")}
playBtn.addEventListener("click",(async()=>{isPlaying?(audio.pause(),playBtn.textContent="▶️"):(await audio.play(),playBtn.textContent="⏸️"),isPlaying=!isPlaying}));
audio.addEventListener("timeupdate",(()=>{const e=audio.currentTime/audio.duration*100;progressBar.style.width=(isFinite(e)?e:0)+"%",timeDisplay.textContent=formatTime(audio.currentTime)+" / "+formatTime(audio.duration)}));
progress.addEventListener("click",(e=>{const t=progress.getBoundingClientRect(),n=(e.clientX-t.left)/t.width;isFinite(audio.duration)&&(audio.currentTime=n*audio.duration)}));

const canvas=document.getElementById("c"),renderer=new THREE.WebGLRenderer({canvas:canvas,antialias:!0});
renderer.setPixelRatio(Math.min(window.devicePixelRatio||1,2)),renderer.setSize(innerWidth,innerHeight);
const scene=new THREE.Scene,camera=new THREE.PerspectiveCamera(60,innerWidth/innerHeight,.1,5e3);
let targetDist=300,currentDist=300,rotX=.2,rotY=0;

// Estrellas de fondo
function createStars(e=5000,t=3000){const n=new THREE.BufferGeometry,a=new Float32Array(3*e);for(let n=0;n<e;n++){const e=t*(.1+Math.random()),r=Math.random()*Math.PI*2,i=Math.acos(2*Math.random()-1);a[3*n+0]=e*Math.sin(i)*Math.cos(r),a[3*n+1]=e*Math.cos(i),a[3*n+2]=e*Math.sin(i)*Math.sin(r)}n.setAttribute("position",new THREE.BufferAttribute(a,3)),scene.add(new THREE.Points(n,new THREE.PointsMaterial({size:1.8,color:16777215,transparent:true,opacity:0.8})))}
createStars();

// Estrellas fugaces
let shootingStars = [];
const shootMat = new THREE.LineBasicMaterial({color: 0xffffff, transparent: true, opacity: 1});
function addShootingStar() {
    const pts = [new THREE.Vector3(0,0,0), new THREE.Vector3(40,40,40)];
    const geo = new THREE.BufferGeometry().setFromPoints(pts);
    const line = new THREE.Line(geo, shootMat.clone());
    line.position.set((Math.random()-0.5)*1200, (Math.random()-0.5)*1200, (Math.random()-0.5)*1200);
    line.userData = { vel: new THREE.Vector3(-12,-12,-12) };
    scene.add(line);
    shootingStars.push(line);
}

const coreMat=new THREE.MeshPhongMaterial({color:0xffffff,transparent:!0,opacity:.6,shininess:200}),core=new THREE.Mesh(new THREE.SphereGeometry(40,64,64),coreMat);
scene.add(core);

// Texto Central (Con grupo para rotación 360)
const textPivot = new THREE.Group();
scene.add(textPivot);
function makeCenterTextTexture(e){const t=document.createElement("canvas");t.width=1024,t.height=256;const n=t.getContext("2d");n.font="bold 75px Arial",n.textAlign="center",n.textBaseline="middle",n.fillStyle="#ffffff",n.shadowColor="#ff0044",n.shadowBlur=40,n.fillText(e,t.width/2,t.height/2);return new THREE.CanvasTexture(t)}
const centerSprite=new THREE.Sprite(new THREE.SpriteMaterial({map:makeCenterTextTexture("TE AMO MUCHO ❤️ LESLIE"),transparent:!0}));
centerSprite.scale.set(160,40,1); 
textPivot.add(centerSprite);

// Brillo central
function makeGlow(e=768){const a=document.createElement("canvas");a.width=a.height=e;const r=a.getContext("2d"),i=r.createRadialGradient(e/2,e/2,20,e/2,e/2,e/2);i.addColorStop(0,"rgba(255,255,255,1)"),i.addColorStop(.4,"rgba(255,100,0,0.8)"),i.addColorStop(1,"rgba(0,0,0,0)");r.fillStyle=i,r.fillRect(0,0,e,e);return new THREE.CanvasTexture(a)}
const glow=new THREE.Sprite(new THREE.SpriteMaterial({map:makeGlow(),transparent:!0,depthWrite:!1,blending:THREE.AdditiveBlending}));
glow.scale.set(500,500,1); scene.add(glow);

const ring1=new THREE.Mesh(new THREE.RingGeometry(65,85,128),new THREE.MeshBasicMaterial({color:0xff6600,transparent:!0,side:THREE.DoubleSide,opacity:0.7}));
ring1.rotation.x=Math.PI/2; scene.add(ring1);

// Palabras flotantes originales
const WORDS=[],baseWords=["💖 Mi amor","🌞 Mi sol","🌎 Mi mundo","✨ Brillas","❤️ Te amo","🌌 Universo","👑 Reina","🌠 Estrella","💫 Mi cielo","🔥 Siempre tú","🎶 Tu risa","🦋 Libertad","💎 Eres todo","🙏 Gracias","💕 Cariño","🌹 Amor eterno","🤗 Abrazos","🌸 Esperanza","🌈 Alegría","🌟 Contigo","🧸 Ternura","🎁 Mi razón","🌙 Mi destino","💌 Recuerdos","🕊️ Mi paz","🪐 Mi universo","🌊 Mi calma","💡 Mi luz","🍒 Dulzura","🥰 Mi vida","🎇 Felicidad","🌻 Alegría","🌺 Mi flor","💜 Eternidad","🌟 Sueños","✨ Magia","🎵 Canción","🔥 Pasión","⭐ Mi estrella","🌴 Mi paraíso","🌄 Amanecer","🌃 Noche contigo","🎉 Mi fiesta","💫 Inspiración","🌷 Siempre juntos","🎀 Mi ternura","🍀 Mi fortuna","🪞 Mi reflejo"];
for(let e=0;e<6;e++)WORDS.push(...baseWords);
function makeTextTexture(e,t){const n=document.createElement("canvas");n.width=512,n.height=128;const a=n.getContext("2d");a.font="bold 60px Arial",a.textAlign="center",a.textBaseline="middle",a.fillStyle="#fff",a.shadowColor=t,a.shadowBlur=30,a.fillText(e,n.width/2,n.height/2);return new THREE.CanvasTexture(n)}
const COLORS=["#ff66ff","#66ccff","#ffd36b","#ff9966","#8df59a","#ffa0f8","#c6a7ff","#ff4444","#44ff99","#99ccff"],textGroup=new THREE.Group;scene.add(textGroup);
for(let e=0;e<WORDS.length;e++){const t=makeTextTexture(WORDS[e],COLORS[e%COLORS.length]),n=new THREE.SpriteMaterial({map:t,transparent:!0}),a=new THREE.Sprite(n);a.scale.set(50,16,1);const r=Math.acos(2*Math.random()-1),i=Math.random()*Math.PI*2,o=160+130*Math.random();a.position.set(o*Math.sin(r)*Math.cos(i),o*Math.cos(r),o*Math.sin(r)*Math.sin(i)),a.userData={phi:r,theta:i,radius:o,speed:.001+.0015*Math.random()},textGroup.add(a)}

// Controles (Zoom y Movimiento)
let dragging=!1,lastX=0,lastY=0;
function onDown(e){dragging=!0;const t=e.touches?e.touches[0]:e;lastX=t.clientX,lastY=t.clientY}
function onMove(e){if(!dragging)return;const t=e.touches?e.touches[0]:e,n=(t.clientX-lastX)/innerWidth,a=(t.clientY-lastY)/innerHeight;rotY-=3*n,rotX=Math.max(-1.2,Math.min(1.2,rotX-2.2*a)),lastX=t.clientX,lastY=t.clientY}
function onUp(){dragging=!1}
addEventListener("mousedown",onDown),addEventListener("mousemove",onMove),addEventListener("mouseup",onUp),addEventListener("touchstart",onDown,{passive:!0}),addEventListener("touchmove",onMove,{passive:!0}),addEventListener("touchend",onUp,{passive:!0}),addEventListener("wheel",(e=>{targetDist+=.3*e.deltaY,targetDist=Math.max(150,Math.min(800,targetDist))}),{passive:!0});
let pinch=0;addEventListener("touchmove",(e=>{if(e.touches&&2===e.touches.length){e.preventDefault();const t=Math.hypot(e.touches[0].clientX-e.touches[1].clientX,e.touches[0].clientY-e.touches[1].clientY);pinch&&(targetDist+=.8*(pinch-t),targetDist=Math.max(150,Math.min(800,targetDist))),pinch=t}}),{passive:!1}),addEventListener("touchend",(()=>{pinch=0}),{passive:!0});

let t=0;
function tick(){
    requestAnimationFrame(tick),t+=.01;
    
    // Rotación 360 del Texto Central
    textPivot.rotation.y += 0.015;

    // Latido de Color (Naranja <-> Azul)
    const cycle = (Math.sin(t * 0.8) + 1) / 2;
    const col1 = new THREE.Color(0xff6600), col2 = new THREE.Color(0x0088ff);
    const mixedCol = col1.lerp(col2, cycle);
    glow.material.color.copy(mixedCol);
    ring1.material.color.copy(mixedCol);
    
    ring1.rotation.z+=.004;
    const pulse=1+.05*Math.sin(3*t); core.scale.set(pulse,pulse,pulse);
    glow.scale.set(500*pulse,500*pulse,1);

    // Animación de palabras
    textGroup.children.forEach((e=>{e.material.opacity=.8+.2*Math.sin(2*t),e.userData.theta+=e.userData.speed,e.position.x=e.userData.radius*Math.sin(e.userData.phi)*Math.cos(e.userData.theta),e.position.z=e.userData.radius*Math.sin(e.userData.phi)*Math.sin(e.userData.theta)}));

    // Estrellas fugaces
    if(Math.random()<0.02) addShootingStar();
    shootingStars.forEach((s,i)=>{
        s.position.add(s.userData.vel);
        s.material.opacity -= 0.015;
        if(s.material.opacity<=0){scene.remove(s); shootingStars.splice(i,1)}
    });

    currentDist+=.08*(targetDist-currentDist);
    const n=Math.cos(rotX),a=Math.sin(rotX),r=Math.cos(rotY),i=Math.sin(rotY);
    camera.position.set(currentDist*i*n,currentDist*a,currentDist*r*n),camera.lookAt(0,0,0),renderer.render(scene,camera)
}
tick();
window.addEventListener("resize",()=>{camera.aspect=innerWidth/innerHeight;camera.updateProjectionMatrix();renderer.setSize(innerWidth,innerHeight)});
</script>
</body>
</html>
