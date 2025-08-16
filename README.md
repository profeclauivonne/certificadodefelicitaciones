# certificadodefelicitaciones
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Certificado de Felicitación - Continuemos Entrenando</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;800;900&family=Playfair+Display:wght@600;700&family=Great+Vibes&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<style>
  :root{
    /* Paleta pastel potente (verde, azul, rosa) */
    --p-green:#AEE5C9;
    --p-blue:#A9D5FF;
    --p-pink:#F9C5D5;
    --ink:#0F1B36;
    --ink-soft:#2C3B5E;
    --paper:#FFFEFD;
    --glow: rgba(169,213,255,.45);
    --glow2: rgba(249,197,213,.35);
  }

  /* Fondo hero con gradientes, rayos y destellos */
  body{
    background:
      radial-gradient(1100px 680px at 0% -10%, rgba(169,213,255,.38), transparent 60%),
      radial-gradient(900px 580px at 100% 15%, rgba(174,229,201,.36), transparent 60%),
      radial-gradient(900px 600px at 50% 110%, rgba(249,197,213,.36), transparent 60%),
      linear-gradient(160deg, #f7fbff 0%, #ffffff 100%);
  }
  .beams{
    position: fixed; inset:0; pointer-events:none; z-index:0;
    background:
      conic-gradient(from 0deg at 50% -20%, rgba(169,213,255,.22), transparent 20% 40%, rgba(249,197,213,.2) 60%, transparent 80% 100%),
      conic-gradient(from 180deg at 50% 120%, rgba(174,229,201,.18), transparent 30% 70%, rgba(169,213,255,.18));
    filter: blur(20px);
    opacity:.7;
  }

  /* Tarjeta principal con borde luminoso */
  .board{
    position: relative;
    border-radius: 30px;
    background: var(--paper);
    box-shadow:
      0 28px 70px rgba(15,27,54,.22),
      0 0 0 10px rgba(255,255,255,.7) inset;
    overflow: hidden;
  }
  .board::before{
    content:"";
    position:absolute; inset:0; padding:2px; border-radius:30px;
    background: linear-gradient(135deg, var(--p-green), var(--p-blue), var(--p-pink));
    -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
    -webkit-mask-composite: xor; mask-composite: exclude;
    pointer-events:none;
  }

  /* Marco interior con líneas finas */
  .inner{
    position: relative;
    border-radius: 22px;
    padding: clamp(22px, 3vw, 54px);
    background:
      linear-gradient(180deg, rgba(255,255,255,.95), rgba(255,255,255,.9)) padding-box;
  }
  .inner::after{
    content:"";
    position:absolute; inset:16px; border-radius:16px;
    border:1.5px dashed rgba(15,27,54,.18);
    pointer-events:none;
  }

  /* Cinta superior destacada */
  .badge{
    display:inline-flex; align-items:center; gap:.6rem;
    padding:.55rem 1.05rem;
    border-radius:999px;
    color:#0d1a33; font-weight:800; letter-spacing:.4px;
    background:
      linear-gradient(90deg, rgba(255,255,255,.85), rgba(255,255,255,.7)) padding-box,
      linear-gradient(90deg, var(--p-green), var(--p-blue), var(--p-pink)) border-box;
    border:2px solid transparent;
    box-shadow: 0 12px 28px rgba(15,27,54,.12);
    text-transform: uppercase;
  }

  .btn{ transition: all .15s ease; }
  .btn:hover{ transform: translateY(-1px); }
  .btn:active{ transform: translateY(0); filter: brightness(.96); }

  /* Sello animado */
  .seal{
    position:relative; width:112px; height:112px; border-radius:999px; overflow:hidden;
    border:3px solid #0f1f3b10; background:#fff;
    box-shadow: inset 0 0 0 2px rgba(23,34,59,.08);
  }
  .seal .ring{
    position:absolute; inset:-25%;
    background: conic-gradient(from 0deg, var(--p-green), var(--p-blue), var(--p-pink), var(--p-green));
    animation: spin 8s linear infinite;
    filter: blur(14px); opacity:.75;
  }
  .seal .center{
    position:absolute; inset:12px; border-radius:999px; background:#fffefe; display:grid; place-items:center;
    border: 1px solid rgba(23,34,59,.1);
  }
  @keyframes spin{ to { transform: rotate(360deg);} }

  /* Frase motivadora */
  .quote{
    background: linear-gradient(90deg, var(--p-green)/30, var(--p-blue)/30, var(--p-pink)/30);
  }

  /* Barra inferior de energía */
  .bar{ height:14px; border-radius: 999px; overflow:hidden; }
  .bar > div{ height:100%; background: linear-gradient(90deg, var(--p-green), var(--p-blue), var(--p-pink)); }

  /* Confeti */
  .confetti{ position:fixed; inset:0; pointer-events:none; z-index:50; }

  /* Pop de celebración */
  .pop{
    animation: pop 1000ms ease;
    box-shadow: 0 26px 70px rgba(15,27,54,.24), 0 0 0 10px var(--glow);
  }
  @keyframes pop{
    0%{ transform: scale(1); }
    35%{ transform: scale(1.02); }
    100%{ transform: scale(1); }
  }

  /* Impresión */
  @page { size: A4; margin: 14mm; }
  @media print{
    body{ background:#fff !important; }
    .no-print{ display:none !important; }
  }
</style>
</head>
<body class="min-h-screen flex items-center justify-center p-6 text-slate-800 antialiased">
  <div class="beams"></div>
  <canvas id="confetti" class="confetti"></canvas>

  <div class="w-full max-w-6xl mx-auto space-y-6 relative z-10">
    <!-- Controles -->
    <div class="no-print rounded-2xl p-5 md:p-6 bg-white/70 backdrop-blur border border-white/60 shadow-xl">
      <div class="flex flex-col md:flex-row md:items-end justify-between gap-4 md:gap-6">
        <div class="flex-1">
          <h1 class="text-2xl md:text-3xl font-extrabold text-slate-900">Certificado de Felicitación</h1>
          <p class="text-slate-600 mt-1">Celebra con confeti y comparte o descarga tu certificado.</p>
        </div>
        <div class="flex flex-wrap items-center gap-3">
          <label class="cursor-pointer">
            <input type="file" id="logoInput" accept="image/*" class="hidden">
            <span class="btn inline-flex items-center gap-2 px-4 py-2 rounded-xl bg-white text-slate-800 border border-slate-200 hover:shadow-md">
              📤 Subir logo
            </span>
          </label>
          <button id="celebrateBtn" class="btn inline-flex items-center gap-2 px-4 py-2 rounded-xl font-semibold text-slate-900 bg-gradient-to-r from-[var(--p-green)] via-[var(--p-blue)] to-[var(--p-pink)] hover:shadow-lg">
            🎉 Celebrar
          </button>
          <button id="downloadBtn" class="btn inline-flex items-center gap-2 px-4 py-2 rounded-xl bg-slate-900 text-white font-semibold hover:shadow-lg">
            ⬇️ Descargar imagen
          </button>
          <button id="printBtn" class="btn inline-flex items-center gap-2 px-4 py-2 rounded-xl bg-white text-slate-800 border border-slate-200 hover:shadow-md">
            🖨️ Imprimir / PDF
          </button>
          <button id="shareBtn" class="btn inline-flex items-center gap-2 px-4 py-2 rounded-xl bg-white text-slate-800 border border-slate-200 hover:shadow-md">
            🔗 Compartir
          </button>
        </div>
      </div>
    </div>

    <!-- Certificado -->
    <section id="card" class="board p-4 md:p-6 lg:p-8">
      <div class="inner">
        <!-- Cabecera -->
        <div class="flex items-center justify-between gap-6">
          <!-- Logo -->
          <div class="flex items-center gap-3">
            <div class="w-20 h-20 md:w-24 md:h-24 rounded-2xl bg-white/85 border border-slate-200 overflow-hidden grid place-items-center">
              <img id="logoPreview" alt="Logo" class="max-w-full max-h-full object-contain opacity-95 hidden">
              <div id="logoPlaceholder" class="text-slate-400 text-xs text-center px-2">Tu logo</div>
            </div>
            <div class="hidden sm:block">
              <div class="text-xs uppercase tracking-widest text-slate-500">Programa</div>
              <div class="font-bold text-xl md:text-2xl text-slate-900">Bienestar Total 21 Días</div>
            </div>
          </div>

          <!-- Cinta central -->
          <div class="flex-1 flex justify-center">
            <span class="badge text-sm md:text-base">¡Felicitaciones por tu logro!</span>
          </div>

          <!-- Sello -->
          <div class="seal">
            <div class="ring"></div>
            <div class="center">
              <div class="text-center">
                <div class="text-[10px] uppercase tracking-widest text-slate-700">Oficial</div>
                <div class="font-['Playfair_Display'] text-lg text-slate-900 -mt-0.5">BT21</div>
              </div>
            </div>
          </div>
        </div>

        <!-- Mensaje principal -->
        <div class="mt-8 text-center">
          <h2 class="font-['Playfair_Display'] text-3xl md:text-5xl text-[var(--ink)] leading-tight">
            Certificado de Felicitación
          </h2>
          <p class="mt-3 max-w-3xl mx-auto text-slate-600">
            Celebramos tu esfuerzo y constancia. Este es solo el comienzo de una vida más activa, más fuerte y más feliz.
          </p>
        </div>

        <!-- Frase motivadora llamativa -->
        <div class="mt-8 md:mt-10 relative overflow-hidden rounded-2xl p-5 md:p-7 bg-gradient-to-r from-[var(--p-green)]/35 via-[var(--p-blue)]/35 to-[var(--p-pink)]/35">
          <div class="absolute -top-28 -left-24 w-80 h-80 rounded-full opacity-30" style="background: radial-gradient(circle, #fff 0%, transparent 60%);"></div>
          <div class="absolute -bottom-24 -right-16 w-72 h-72 rounded-full opacity-25" style="background: radial-gradient(circle, #fff 0%, transparent 60%);"></div>
          <blockquote class="text-center">
            <p class="text-2xl md:text-[28px] font-extrabold text-[var(--ink-soft)] leading-snug">
              “Cada hábito saludable que sostienes hoy es la victoria que impulsa tu próxima meta. Mantén el ritmo, tu cuerpo y tu mente ya están cambiando.”
            </p>
            <p class="mt-2 text-slate-600 text-sm md:text-base">Sigue entrenando conmigo: vamos a por tu mejor versión 💪✨</p>
          </blockquote>
        </div>

        <!-- Llamado a la acción -->
        <div class="mt-8 text-center">
          <div class="inline-flex flex-wrap justify-center gap-3">
            <a id="ctaJoin" class="btn inline-flex items-center gap-2 px-5 py-3 rounded-2xl font-semibold text-slate-900 bg-gradient-to-r from-[var(--p-green)] via-[var(--p-blue)] to-[var(--p-pink)] hover:shadow-lg cursor-pointer">
              🚀 Continuar entrenando
            </a>
            <a id="ctaWhatsApp" class="btn inline-flex items-center gap-2 px-5 py-3 rounded-2xl bg-white text-slate-800 border border-slate-200 hover:shadow-md cursor-pointer">
              💬 Hablar con Claudia
            </a>
          </div>
          <p class="mt-2 text-slate-500 text-sm">Agenda tu próxima sesión o escríbeme para mantener el impulso.</p>
        </div>

        <!-- Firma -->
        <div class="mt-10 grid grid-cols-1 md:grid-cols-[1fr,auto,1fr] items-center gap-6">
          <div class="hidden md:block"></div>
          <div class="text-center">
            <div class="sig-line mx-auto mb-3" style="background: linear-gradient(90deg, transparent 0 48%, rgba(0,0,0,.16) 48% 52%, transparent 52% 100%); background-size: 18px 1px; height:1px; width:260px;"></div>
            <div class="font-['Great_Vibes'] text-3xl md:text-4xl text-[var(--ink)]">Claudia Ivonne Peña Leiva</div>
            <div class="text-slate-600 text-sm mt-1">
              Profesora de Educación Física y Salud · Coach de Bienestar Integral · Directora del Programa
            </div>
          </div>
          <div class="hidden md:block"></div>
        </div>

        <!-- Barra inferior -->
        <div class="mt-10 bar">
          <div></div>
        </div>
      </div>
    </section>

    <div class="no-print text-center text-slate-600">
      Tip: pulsa “Celebrar” para confeti y usa Compartir/Descargar/Imprimir para difundir tu reconocimiento.
    </div>
  </div>

<script>
  // Elementos
  const card = document.getElementById('card');
  const logoInput = document.getElementById('logoInput');
  const logoPreview = document.getElementById('logoPreview');
  const logoPlaceholder = document.getElementById('logoPlaceholder');

  const celebrateBtn = document.getElementById('celebrateBtn');
  const downloadBtn = document.getElementById('downloadBtn');
  const printBtn = document.getElementById('printBtn');
  const shareBtn = document.getElementById('shareBtn');

  const ctaJoin = document.getElementById('ctaJoin');
  const ctaWhatsApp = document.getElementById('ctaWhatsApp');

  // Confeti
  const confettiCanvas = document.getElementById('confetti');
  const ctx = confettiCanvas.getContext('2d');
  let confettiPieces = [];
  let confettiRunning = false;

  // Redimensionar confeti
  function resizeCanvas(){
    confettiCanvas.width = window.innerWidth;
    confettiCanvas.height = window.innerHeight;
  }
  window.addEventListener('resize', resizeCanvas);
  resizeCanvas();

  // Subir logo
  logoInput.addEventListener('change', (e)=>{
    const file = e.target.files[0];
    if(!file) return;
    const reader = new FileReader();
    reader.onload = (evt)=>{
      logoPreview.src = evt.target.result;
      logoPreview.classList.remove('hidden');
      logoPlaceholder.classList.add('hidden');
    };
    reader.readAsDataURL(file);
  });

  // Celebración
  celebrateBtn.addEventListener('click', ()=>{
    popCard();
    fireConfetti();
  });

  function popCard(){
    card.classList.remove('pop'); void card.offsetWidth; card.classList.add('pop');
  }

  function fireConfetti(){
    confettiPieces = [];
    const amount = 240;
    for(let i=0; i<amount; i++){ confettiPieces.push(makePiece()); }
    if(!confettiRunning){
      confettiRunning = true;
      animateConfetti();
      setTimeout(()=>{ confettiRunning = false; }, 2200);
    }
  }

  function makePiece(){
    const colors = ['#AEE5C9','#A9D5FF','#F9C5D5','#7FC8A9','#7DB7FF','#F19BBC','#FFFFFF'];
    return {
      x: Math.random()*confettiCanvas.width,
      y: -10,
      r: 3 + Math.random()*6,
      c: colors[Math.floor(Math.random()*colors.length)],
      s: 1 + Math.random()*2.7,
      a: Math.random()*Math.PI*2,
      w: 0.9 + Math.random()*1.3
    };
  }

  function animateConfetti(){
    ctx.clearRect(0,0,confettiCanvas.width, confettiCanvas.height);
    confettiPieces.forEach(p=>{
      p.y += p.s*3.2;
      p.x += Math.cos(p.a)*p.w;
      p.a += 0.05;
      ctx.beginPath();
      ctx.fillStyle = p.c;
      ctx.arc(p.x, p.y, p.r, 0, Math.PI*2);
      ctx.fill();
    });
    confettiPieces = confettiPieces.filter(p=>p.y < confettiCanvas.height + 10);
    if(confettiRunning || confettiPieces.length){ requestAnimationFrame(animateConfetti); }
  }

  // Descargar como imagen (PNG) usando html2canvas
  let html2canvasLoaded = false;
  function loadHtml2Canvas(){
    return new Promise((res, rej)=>{
      if(html2canvasLoaded) return res();
      const s = document.createElement('script');
      s.src = 'https://cdn.jsdelivr.net/npm/html2canvas@1.4.1/dist/html2canvas.min.js';
      s.onload = ()=>{ html2canvasLoaded = true; res(); };
      s.onerror = rej;
      document.body.appendChild(s);
    });
  }

  downloadBtn.addEventListener('click', async ()=>{
    await loadHtml2Canvas();
    const target = document.querySelector('.inner');
    await new Promise(r=>setTimeout(r,120));
    window.html2canvas(target, { backgroundColor: null, scale: 2 }).then(canvas=>{
      const link = document.createElement('a');
      link.download = `Certificado_Felicitacion.png`;
      link.href = canvas.toDataURL('image/png');
      link.click();
    });
  });

  // Imprimir / PDF
  printBtn.addEventListener('click', ()=> window.print());

  // Compartir (Web Share API si está disponible; si no, copia enlace imagen demo)
  shareBtn.addEventListener('click', async ()=>{
    // Generamos imagen temporal del certificado para compartir si el navegador lo permite
    try{
      await loadHtml2Canvas();
      const target = document.querySelector('.inner');
      await new Promise(r=>setTimeout(r,120));
      const canvas = await window.html2canvas(target, { backgroundColor: null, scale: 2 });
      const dataUrl = canvas.toDataURL('image/png');

      if (navigator.share && navigator.canShare) {
        // Intento de compartir archivo (no todos los navegadores lo soportan)
        const resp = await fetch(dataUrl);
        const blob = await resp.blob();
        const file = new File([blob], 'Certificado.png', { type: 'image/png' });

        if (navigator.canShare({ files: [file] })) {
          await navigator.share({
            title: 'Mi certificado',
            text: '¡Mira mi certificado de felicitación! Continuemos entrenando 💪',
            files: [file]
          });
          return;
        }
      }
      // Fallback: abrir imagen en nueva pestaña
      const w = window.open();
      w.document.write('<title>Certificado</title><img src="'+dataUrl+'" style="width:100%;height:auto;display:block;" />');
    }catch(e){
      alert('Si tu navegador no permite compartir, se abrirá una vista de la imagen para guardar.');
    }
  });

  // CTAs (los dejo listos para personalizar enlaces)
  ctaJoin.addEventListener('click', ()=>{
    alert('Aquí puedes enlazar tu página de inscripción o agenda.');
  });
  ctaWhatsApp.addEventListener('click', ()=>{
    // Reemplaza con tu número en formato internacional, ej: 569XXXXXXXX
    const phone = '569XXXXXXXX';
    const text = encodeURIComponent('Hola Claudia, quiero seguir entrenando y mantener mis hábitos. ¿Me ayudas a agendar mi próxima sesión?');
    window.open(`https://wa.me/${phone}?text=${text}`, '_blank');
  });
</script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9702a0a08354a0fe',t:'MTc1NTM2NTA4OS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
