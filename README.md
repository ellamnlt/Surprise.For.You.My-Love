<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  .page { min-height: 100vh; padding: 2rem 1rem; font-family: var(--font-sans); }
  .hero { text-align: center; padding: 3rem 1rem 2rem; position: relative; overflow: hidden; }
  .floating { animation: floatUp 3s ease-in-out infinite; }
  @keyframes floatUp { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)} }
  .confetti-wrap { position: absolute; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; overflow: hidden; }
  .c-bit { position: absolute; width: 8px; height: 8px; border-radius: 2px; opacity: 0; animation: fall linear infinite; }
  @keyframes fall { 0%{opacity:1;transform:translateY(-20px) rotate(0deg)} 100%{opacity:0;transform:translateY(400px) rotate(720deg)} }
  .section { background: var(--color-background-primary); border: 0.5px solid var(--color-border-tertiary); border-radius: var(--border-radius-lg); padding: 1.5rem; margin: 1rem auto; max-width: 680px; }
  .section-title { font-size: 13px; font-weight: 500; color: var(--color-text-secondary); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 1rem; }
  .upload-area { border: 1.5px dashed var(--color-border-secondary); border-radius: var(--border-radius-md); padding: 2rem; text-align: center; cursor: pointer; transition: background 0.2s; position: relative; }
  .upload-area:hover { background: var(--color-background-secondary); }
  .upload-area input { position: absolute; inset: 0; opacity: 0; cursor: pointer; }
  .upload-label { font-size: 14px; color: var(--color-text-secondary); margin-top: 0.5rem; display: block; }
  .preview-img { width: 100%; border-radius: var(--border-radius-md); margin-top: 1rem; display: none; object-fit: cover; }
  .preview-portrait { max-height: 340px; object-fit: contain; }
  .heart-pulse { animation: pulse 1.5s ease-in-out infinite; display: inline-block; }
  @keyframes pulse { 0%,100%{transform:scale(1)} 50%{transform:scale(1.2)} }
  .big-stamp { display: inline-flex; align-items: center; justify-content: center; gap: 0.5rem; background: #E1F5EE; color: #0F6E56; border: 2px solid #1D9E75; border-radius: 50px; padding: 0.6rem 1.5rem; font-size: 1.1rem; font-weight: 500; margin: 1rem 0; }
  .promise-card { background: var(--color-background-secondary); border-left: 3px solid #D4537E; border-radius: 0 var(--border-radius-md) var(--border-radius-md) 0; padding: 1rem 1.25rem; margin: 1rem 0; }
  .message-card { background: var(--color-background-secondary); border-radius: var(--border-radius-lg); padding: 1.5rem; margin-top: 1rem; line-height: 1.9; font-size: 1rem; color: var(--color-text-primary); }
  .highlight { color: #0F6E56; font-weight: 500; }
  .highlight-love { color: #993556; font-weight: 500; }
  .reveal-btn { display: block; width: 100%; max-width: 300px; margin: 1.5rem auto; padding: 0.9rem 2rem; background: #1D9E75; color: #fff; border: none; border-radius: 50px; font-size: 1rem; font-weight: 500; cursor: pointer; transition: transform 0.15s, background 0.2s; }
  .reveal-btn:hover { background: #0F6E56; transform: scale(1.03); }
  .reveal-btn:active { transform: scale(0.97); }
  .hidden { display: none; }
  .fade-in { animation: fadeIn 0.8s ease forwards; }
  @keyframes fadeIn { from{opacity:0;transform:translateY(20px)} to{opacity:1;transform:translateY(0)} }
  .photo-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .photo-slot { display: flex; flex-direction: column; gap: 0.5rem; }
  .photo-tag { font-size: 12px; color: var(--color-text-secondary); font-weight: 500; }
  .divider { height: 0.5px; background: var(--color-border-tertiary); margin: 1.5rem 0; }
  .steps { display: flex; flex-direction: column; gap: 0.75rem; margin-top: 0.5rem; }
  .step { display: flex; align-items: flex-start; gap: 0.75rem; }
  .step-num { width: 26px; height: 26px; border-radius: 50%; background: #E1F5EE; color: #0F6E56; font-size: 12px; font-weight: 500; display: flex; align-items: center; justify-content: center; flex-shrink: 0; margin-top: 2px; }
  .step-text { font-size: 0.9rem; color: var(--color-text-primary); line-height: 1.6; }
  .footer-love { text-align: center; padding: 2rem 1rem 3rem; color: var(--color-text-secondary); font-size: 0.9rem; }
</style>

<div class="page">
  <div class="confetti-wrap" id="confetti"></div>

  <div class="hero">
    <div class="floating" style="font-size: 3rem; margin-bottom: 1rem;">🌍</div>
    <h1 style="font-size: 2rem; font-weight: 500; color: var(--color-text-primary); line-height: 1.3;">I'm going ahead —<br>but I'm coming back for you</h1>
    <p style="color: var(--color-text-secondary); margin-top: 0.75rem; font-size: 1rem;">A promise, not a goodbye</p>
  </div>

  <div class="section" id="reveal-section">
    <p class="section-title">To my love — tap to open</p>
    <div style="text-align: center; padding: 1rem 0;">
      <div style="font-size: 2.5rem; margin-bottom: 1rem;">💌</div>
      <p style="color: var(--color-text-secondary); font-size: 0.95rem;">I have something big to share with you...</p>
      <button class="reveal-btn" onclick="revealMessage()">Open your surprise ❤️</button>
    </div>
  </div>

  <div class="section hidden fade-in" id="message-section">
    <p class="section-title">The news</p>
    <div style="text-align: center; margin-bottom: 1rem;">
      <div class="big-stamp">
        <i class="ti ti-check" aria-hidden="true"></i> Visa approved 🇬🇧
      </div>
    </div>

    <div class="message-card">
      <p>My love,</p>
      <br>
      <p>My <span class="highlight">visa has been approved.</span> I'm going to the UK.</p>
      <br>
      <p>After <span class="highlight">15 long years</span>, I am finally going to see my mom again. I have waited so long for this moment — and it's finally here.</p>
      <br>
      <p>But I need you to know something important: <span class="highlight-love">this is not goodbye.</span> I am going first, yes — but everything I will do there, every shift I work, every penny I save — it will all be for <span class="highlight-love">us.</span></p>
      <br>
      <p>I will <span class="highlight">work hard</span>, build our foundation, and I will <span class="highlight">petition for you</span> as soon as I possibly can. I will do everything — everything — to make sure we are together again, and this time, <span class="highlight-love">in the same country, under the same sky.</span></p>
      <br>
      <p>Distance is temporary. <span class="highlight-love">We are not.</span></p>
      <br>
      <p style="color: var(--color-text-secondary); font-size: 0.9rem;">With all my love across every mile,</p>
      <p style="font-weight: 500; font-size: 1.05rem; margin-top: 0.25rem;">Your person <span class="heart-pulse">❤️</span></p>
    </div>

    <div class="divider"></div>

    <p class="section-title">My promise to you</p>
    <div class="steps">
      <div class="step">
        <div class="step-num">1</div>
        <div class="step-text"><strong style="font-weight:500;">I go first</strong> — I settle in, find my footing, and reunite with my mom after 15 years</div>
      </div>
      <div class="step">
        <div class="step-num">2</div>
        <div class="step-text"><strong style="font-weight:500;">I work hard</strong> — every day with you in mind, building something real for both of us</div>
      </div>
      <div class="step">
        <div class="step-num">3</div>
        <div class="step-text"><strong style="font-weight:500;">I petition for you</strong> — I will not rest until I have done everything possible to bring you to me</div>
      </div>
      <div class="step">
        <div class="step-num">4</div>
        <div class="step-text"><strong style="font-weight:500;">We are together again</strong> — and then the whole world is ours to explore 🌍</div>
      </div>
    </div>

    <div class="promise-card" style="margin-top: 1.5rem;">
      <p style="font-size: 0.95rem; color: var(--color-text-primary); line-height: 1.7;">
        <span class="highlight-love">"Wait for me.</span> I will do everything I can so we can be together. I love you so much — more than any visa, any distance, any ocean between us."
      </p>
    </div>

    <div class="divider"></div>

    <p class="section-title">Our journey documents</p>
    <div class="photo-grid">
      <div class="photo-slot">
        <span class="photo-tag"><i class="ti ti-plane" aria-hidden="true" style="font-size:13px; margin-right:4px;"></i>Flight details</span>
        <div class="upload-area" id="flight-area" onclick="document.getElementById('flight-input').click()">
          <input type="file" id="flight-input" accept="image/*" onchange="previewPhoto(this,'flight-preview','flight-area')">
          <i class="ti ti-upload" aria-hidden="true" style="font-size:24px; color: var(--color-text-secondary);"></i>
          <span class="upload-label">Tap to upload<br><span style="font-size:11px;">Landscape photo</span></span>
          <img id="flight-preview" class="preview-img" alt="Flight details">
        </div>
      </div>
      <div class="photo-slot">
        <span class="photo-tag"><i class="ti ti-id" aria-hidden="true" style="font-size:13px; margin-right:4px;"></i>Visa status</span>
        <div class="upload-area" id="visa-area" onclick="document.getElementById('visa-input').click()">
          <input type="file" id="visa-input" accept="image/*" onchange="previewPhoto(this,'visa-preview','visa-area')">
          <i class="ti ti-upload" aria-hidden="true" style="font-size:24px; color: var(--color-text-secondary);"></i>
          <span class="upload-label">Tap to upload<br><span style="font-size:11px;">Portrait photo</span></span>
          <img id="visa-preview" class="preview-img preview-portrait" alt="Visa status">
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <div style="text-align: center;">
      <p style="font-size: 1.1rem; margin-bottom: 0.5rem;">✈️ → 🇬🇧 → 💪 → 📋 → 🤝 → 🌍</p>
      <p style="font-size: 0.85rem; color: var(--color-text-secondary);">Go · Settle · Work hard · Petition · Reunite · Explore the world together</p>
    </div>
  </div>

  <div class="footer-love hidden" id="footer">
    <p>I love you so much. Wait for me. 🥹❤️</p>
    <p style="margin-top: 0.25rem; font-size: 0.8rem;">This is just the beginning of our story.</p>
  </div>
</div>

<script>
  function makeConfetti() {
    const wrap = document.getElementById('confetti');
    const colors = ['#1D9E75','#D4537E','#FAC775','#378ADD','#9FE1CB','#F0997B'];
    for (let i = 0; i < 40; i++) {
      const bit = document.createElement('div');
      bit.className = 'c-bit';
      bit.style.left = Math.random() * 100 + '%';
      bit.style.background = colors[Math.floor(Math.random() * colors.length)];
      bit.style.animationDuration = (2 + Math.random() * 3) + 's';
      bit.style.animationDelay = (Math.random() * 2) + 's';
      bit.style.width = (6 + Math.random() * 8) + 'px';
      bit.style.height = (6 + Math.random() * 8) + 'px';
      wrap.appendChild(bit);
    }
    setTimeout(() => { wrap.innerHTML = ''; }, 5000);
  }

  function revealMessage() {
    document.getElementById('reveal-section').style.display = 'none';
    document.getElementById('message-section').classList.remove('hidden');
    document.getElementById('footer').classList.remove('hidden');
    makeConfetti();
  }

  function previewPhoto(input, previewId, areaId) {
    const file = input.files[0];
    if (!file) return;
    const reader = new FileReader();
    reader.onload = function(e) {
      const img = document.getElementById(previewId);
      img.src = e.target.result;
      img.style.display = 'block';
      const area = document.getElementById(areaId);
      area.querySelector('.upload-label').style.display = 'none';
      area.querySelector('.ti-upload').style.display = 'none';
    };
    reader.readAsDataURL(file);
  }
</script>
