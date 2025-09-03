<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Image Color Picker • HEX & RGB</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    :root { --bg: #0b1020; --panel:#0f172a; --muted:#94a3b8; }
    html, body { height: 100%; }
    body { font-family: Inter, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; background: linear-gradient(120deg, #0b1020, #111827); }
    .card { background: rgba(15, 23, 42, 0.7); backdrop-filter: blur(8px); border: 1px solid rgba(148, 163, 184, 0.15); }
    .dropzone { border: 2px dashed rgba(148, 163, 184, 0.35); }
    .swatch { border: 1px solid rgba(0,0,0,.2); box-shadow: inset 0 0 0 1px rgba(255,255,255,.08); }
    .btn { transition: transform .06s ease; }
    .btn:active { transform: translateY(1px); }
  </style>
</head>
<body class="text-slate-100">
  <div class="max-w-6xl mx-auto p-6">
    <header class="mb-6 flex items-center justify-between">
      <h1 class="text-2xl sm:text-3xl font-bold tracking-tight">🎯 Image Color Picker <span class="text-slate-400 font-semibold">HEX & RGB</span></h1>
      <div class="flex gap-2">
        <button id="btnDownload" class="btn px-4 py-2 rounded-xl bg-indigo-600 hover:bg-indigo-500 text-white text-sm">Download PNG of Palette</button>
        <a href="#" id="btnReset" class="btn px-4 py-2 rounded-xl bg-slate-700 hover:bg-slate-600 text-sm">Reset</a>
      </div>
    </header>

    <!-- Upload / Dropzone -->
    <section class="card rounded-2xl p-5 mb-6">
      <div id="dropzone" class="dropzone rounded-xl p-6 flex flex-col sm:flex-row items-center gap-4 justify-between">
        <div class="flex items-center gap-4">
          <label for="fileInput" class="px-4 py-2 rounded-xl bg-indigo-600 hover:bg-indigo-500 text-white text-sm cursor-pointer">Upload Image</label>
          <input id="fileInput" type="file" accept="image/*" class="hidden" />
          <button id="btnEyedropper" class="btn px-4 py-2 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white text-sm">Use Eyedropper</button>
        </div>
        <p class="text-slate-300 text-sm">or drag & drop an image here • Click anywhere on the image to sample a color</p>
      </div>
    </section>

    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
      <!-- Image Preview -->
      <section class="card rounded-2xl p-4 lg:col-span-2">
        <div class="relative aspect-video bg-slate-900/60 rounded-xl overflow-hidden flex items-center justify-center">
          <img id="imgPreview" alt="preview" class="max-h-full max-w-full hidden select-none" />
          <div id="placeholder" class="text-center p-8 text-slate-400">
            <div class="text-6xl mb-3">🖼️</div>
            <p class="font-medium">Upload an image to begin.</p>
            <p class="text-sm text-slate-500 mt-1">Supported: JPG, PNG, GIF, WebP, BMP</p>
          </div>
          <canvas id="canvas" class="hidden"></canvas>
        </div>
      </section>

      <!-- Output Panel -->
      <aside class="card rounded-2xl p-5 space-y-5">
        <div>
          <h2 class="text-lg font-semibold mb-3">Picked Color</h2>
          <div class="flex items-center gap-4">
            <div id="pickedSwatch" class="swatch h-16 w-16 rounded-xl bg-transparent"></div>
            <div class="space-y-1">
              <div class="flex items-center gap-2">
                <code id="hexOut" class="px-2 py-1 rounded bg-slate-800 text-sm">#—</code>
                <button class="btn px-2 py-1 rounded bg-slate-700 hover:bg-slate-600 text-xs" data-copy="hexOut">Copy</button>
              </div>
              <div class="flex items-center gap-2">
                <code id="rgbOut" class="px-2 py-1 rounded bg-slate-800 text-sm">rgb(—)</code>
                <button class="btn px-2 py-1 rounded bg-slate-700 hover:bg-slate-600 text-xs" data-copy="rgbOut">Copy</button>
              </div>
            </div>
          </div>
        </div>

        <div class="border-t border-slate-700/50 pt-4">
          <div class="flex items-center justify-between">
            <h2 class="text-lg font-semibold">Quick Palette</h2>
            <button id="btnPalette" class="btn px-3 py-1.5 rounded-xl bg-indigo-600 hover:bg-indigo-500 text-sm">Generate</button>
          </div>
          <p class="text-xs text-slate-400 mt-1">Fast approx. from sampled pixels. Click a swatch to copy HEX.</p>
          <div id="palette" class="grid grid-cols-6 gap-2 mt-3"></div>
        </div>

        <div class="border-t border-slate-700/50 pt-4">
          <h2 class="text-lg font-semibold mb-2">Accessibility</h2>
          <label class="text-xs text-slate-400">Contrast vs. white text (AA ≥ 4.5)</label>
          <div class="grid grid-cols-2 gap-2 mt-2">
            <div id="contrastAA" class="rounded-xl p-3 bg-slate-800 text-sm">—</div>
            <div id="contrastAAA" class="rounded-xl p-3 bg-slate-800 text-sm">—</div>
          </div>
        </div>
      </aside>
    </div>
  </div>

  <script>
    const fileInput = document.getElementById('fileInput');
    const dropzone = document.getElementById('dropzone');
    const img = document.getElementById('imgPreview');
    const placeholder = document.getElementById('placeholder');
    const canvas = document.getElementById('canvas');
    const hexOut = document.getElementById('hexOut');
    const rgbOut = document.getElementById('rgbOut');
    const swatch = document.getElementById('pickedSwatch');
    const btnPalette = document.getElementById('btnPalette');
    const paletteEl = document.getElementById('palette');
    const btnReset = document.getElementById('btnReset');
    const btnDownload = document.getElementById('btnDownload');
    const btnEyedropper = document.getElementById('btnEyedropper');
    const contrastAA = document.getElementById('contrastAA');
    const contrastAAA = document.getElementById('contrastAAA');

    let ctx, imgScale = 1, imgOffset = {x:0, y:0};

    function showImage(src) {
      img.onload = () => {
        placeholder.classList.add('hidden');
        img.classList.remove('hidden');
        // Draw to offscreen canvas at natural size for pixel-accurate reads
        canvas.width = img.naturalWidth;
        canvas.height = img.naturalHeight;
        ctx = canvas.getContext('2d', { willReadFrequently: true });
        ctx.drawImage(img, 0, 0);
        calcScale();
      };
      img.src = src;
    }

    function calcScale(){
      // Calculate display scale & offset so we can map click -> natural pixels
      const container = img.parentElement.getBoundingClientRect();
      const iw = img.naturalWidth, ih = img.naturalHeight;
      const cw = container.width, ch = container.height;
      const s = Math.min(cw/iw, ch/ih);
      const dispW = iw * s, dispH = ih * s;
      img.style.width = dispW + 'px';
      img.style.height = dispH + 'px';
      imgScale = s;
      imgOffset.x = (cw - dispW)/2;
      imgOffset.y = (ch - dispH)/2;
      img.style.marginLeft = imgOffset.x + 'px';
      img.style.marginTop = imgOffset.y + 'px';
      img.style.objectFit = 'contain';
    }

    function rgbToHex(r,g,b){
      return '#' + [r,g,b].map(v=> v.toString(16).padStart(2,'0')).join('').toUpperCase();
    }

    function luminance(r,g,b){
      const a=[r,g,b].map(v=>{v/=255;return v<=0.03928?v/12.92:Math.pow((v+0.055)/1.055,2.4)});
      return 0.2126*a[0]+0.7152*a[1]+0.0722*a[2];
    }

    function contrastRatio(rgb, against=[255,255,255]){
      const L1 = luminance(rgb[0],rgb[1],rgb[2]);
      const L2 = luminance(against[0],against[1],against[2]);
      const lighter = Math.max(L1,L2), darker = Math.min(L1,L2);
      return (lighter + 0.05) / (darker + 0.05);
    }

    function setPicked(r,g,b){
      const hex = rgbToHex(r,g,b);
      hexOut.textContent = hex;
      rgbOut.textContent = `rgb(${r}, ${g}, ${b})`;
      swatch.style.background = hex;
      // contrast vs white text on this color
      const cr = contrastRatio([r,g,b],[255,255,255]);
      const crBlack = contrastRatio([r,g,b],[0,0,0]);
      contrastAA.textContent = `White text contrast: ${cr.toFixed(2)} (AA ${cr>=4.5?'✓':'✗'})`;
      contrastAAA.textContent = `Black text contrast: ${crBlack.toFixed(2)} (AA ${crBlack>=4.5?'✓':'✗'})`;
      contrastAA.style.background = hex;
      contrastAA.style.color = cr>=4.5? 'white' : 'black';
      contrastAAA.style.background = hex;
      contrastAAA.style.color = crBlack>=4.5? 'black' : 'white';
    }

    function pickAtClientPoint(evt){
      if(!ctx) return;
      const rect = img.parentElement.getBoundingClientRect();
      // account for scroll + container offset + image offset inside container
      const x = (evt.clientX - rect.left - imgOffset.x) / imgScale;
      const y = (evt.clientY - rect.top - imgOffset.y) / imgScale;
      const ix = Math.max(0, Math.min(canvas.width-1, Math.round(x)));
      const iy = Math.max(0, Math.min(canvas.height-1, Math.round(y)));
      const [r,g,b,a] = ctx.getImageData(ix, iy, 1, 1).data;
      if(a===0) return; // transparent
      setPicked(r,g,b);
    }

    // Generate a quick palette by sampling every Nth pixel and bucketing colors
    function generatePalette(samplesStep=10, buckets=6){
      if(!ctx) return;
      const w = canvas.width, h = canvas.height;
      const data = ctx.getImageData(0,0,w,h).data;
      const map = new Map();
      for(let y=0; y<h; y+=samplesStep){
        for(let x=0; x<w; x+=samplesStep){
          const i = (y*w + x)*4;
          const r = data[i], g=data[i+1], b=data[i+2], a=data[i+3];
          if(a<200) continue; // skip transparent
          // coarse quantize to reduce unique keys (round to nearest 16)
          const rq = (r>>4)<<4, gq=(g>>4)<<4, bq=(b>>4)<<4;
          const key = (rq<<16) | (gq<<8) | bq;
          map.set(key, (map.get(key)||0)+1);
        }
      }
      const sorted = [...map.entries()].sort((a,b)=>b[1]-a[1]).slice(0, Math.max(6,buckets));
      paletteEl.innerHTML = '';
      sorted.forEach(([key])=>{
        const r = (key>>16)&255, g=(key>>8)&255, b=key&255;
        const hex = rgbToHex(r,g,b);
        const chip = document.createElement('button');
        chip.className = 'swatch h-10 rounded-xl w-full';
        chip.style.background = hex;
        chip.title = hex;
        chip.addEventListener('click', ()=> copyText(hex));
        const label = document.createElement('div');
        label.className = 'text-[10px] text-center mt-1 text-slate-300';
        label.textContent = hex;
        const wrapper = document.createElement('div');
        wrapper.className = 'flex flex-col items-center';
        wrapper.appendChild(chip);
        wrapper.appendChild(label);
        paletteEl.appendChild(wrapper);
      });
    }

    function copyText(text){
      navigator.clipboard.writeText(text).then(()=> toast('Copied!')).catch(()=>{});
    }

    function toast(msg){
      const t = document.createElement('div');
      t.textContent = msg;
      t.className = 'fixed bottom-4 left-1/2 -translate-x-1/2 px-3 py-2 rounded-xl bg-slate-800/90 text-slate-100 text-sm shadow-lg';
      document.body.appendChild(t);
      setTimeout(()=>{ t.remove(); }, 1100);
    }

    // Events
    fileInput.addEventListener('change', (e)=>{
      const f = e.target.files?.[0];
      if(!f) return;
      const url = URL.createObjectURL(f);
      showImage(url);
    });

    ;['dragenter','dragover'].forEach(evt=> dropzone.addEventListener(evt, (e)=>{ e.preventDefault(); dropzone.classList.add('ring-2','ring-indigo-500'); }));
    ;['dragleave','drop'].forEach(evt=> dropzone.addEventListener(evt, (e)=>{ e.preventDefault(); dropzone.classList.remove('ring-2','ring-indigo-500'); }));

    dropzone.addEventListener('drop', (e)=>{
      const f = e.dataTransfer.files?.[0];
      if(f && f.type.startsWith('image/')){
        showImage(URL.createObjectURL(f));
      }
    });

    // Click to sample
    img.addEventListener('click', pickAtClientPoint);
    window.addEventListener('resize', ()=> img.src && calcScale());

    // Copy buttons
    document.querySelectorAll('[data-copy]').forEach(btn=>{
      btn.addEventListener('click', ()=>{
        const id = btn.getAttribute('data-copy');
        const el = document.getElementById(id);
        copyText(el.textContent);
      })
    });

    // Palette
    btnPalette.addEventListener('click', ()=> generatePalette());

    // Reset
    btnReset.addEventListener('click', (e)=>{
      e.preventDefault();
      img.src='';
      img.classList.add('hidden');
      placeholder.classList.remove('hidden');
      paletteEl.innerHTML='';
      hexOut.textContent = '#—';
      rgbOut.textContent = 'rgb(—)';
      swatch.style.background='transparent';
      contrastAA.textContent = '—';
      contrastAAA.textContent = '—';
    });

    // Download simple palette PNG
    btnDownload.addEventListener('click', ()=>{
      if(!paletteEl.children.length){ generatePalette(); }
      const c = document.createElement('canvas');
      const colors = [...paletteEl.querySelectorAll('div > div')].map(el=> el.textContent).filter(Boolean);
      const w = 600, h = 160; c.width=w; c.height=h;
      const g = c.getContext('2d');
      g.fillStyle = '#0b1020'; g.fillRect(0,0,w,h);
      const sw = Math.floor((w-40)/colors.length); let x=20;
      colors.forEach((hex,i)=>{ g.fillStyle = hex; g.fillRect(x,30,sw,70); g.fillStyle = '#ffffff'; g.font='14px Inter, Arial'; g.fillText(hex, x+8, 120); x+=sw; });
      const link = document.createElement('a'); link.download = 'palette.png'; link.href = c.toDataURL('image/png'); link.click();
    });

    // Eyedropper API (system-wide)
    btnEyedropper.addEventListener('click', async ()=>{
      if('EyeDropper' in window){
        try{
          const ed = new EyeDropper();
          const result = await ed.open();
          // result.sRGBHex like "#aabbcc"
          const hex = result.sRGBHex.toUpperCase();
          const r = parseInt(hex.substr(1,2),16), g=parseInt(hex.substr(3,2),16), b=parseInt(hex.substr(5,2),16);
          setPicked(r,g,b);
        }catch(err){ /* user cancelled */ }
      }else{
        toast('Eyedropper not supported in this browser');
      }
    });
  </script>
</body>
</html>
