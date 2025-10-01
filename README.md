# Orangaring
Pemula....
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Roleplay Swap — Aziz Rahman Widiyanto</title>
  <style>
    :root{--bg:#0f1724;--card:#0b1220;--accent:#7dd3fc;--muted:#94a3b8;--glass: rgba(255,255,255,0.03)}
    *{box-sizing:border-box;font-family:Inter,ui-sans-serif,system-ui,Segoe UI,Roboto,"Helvetica Neue",Arial}
    body{margin:0;background:linear-gradient(180deg,#071024 0%,#07182a 100%);color:#e6eef8;min-height:100vh;display:flex;align-items:center;justify-content:center;padding:24px}
    .wrapper{width:100%;max-width:900px}
    header{display:flex;align-items:center;gap:16px;margin-bottom:18px}
    .logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#60a5fa);display:flex;align-items:center;justify-content:center;font-weight:700;color:#012a36}
    h1{margin:0;font-size:18px}
    p.lead{margin:0;color:var(--muted);font-size:13px}

    .card{background:var(--card);padding:18px;border-radius:12px;box-shadow:0 6px 20px rgba(2,6,23,0.6);backdrop-filter:blur(6px)}
    .grid{display:grid;grid-template-columns:1fr 360px;gap:16px}
    @media (max-width:880px){.grid{grid-template-columns:1fr} .right{order:2}}

    label{display:block;font-size:13px;color:var(--muted);margin-bottom:6px}
    input[type=text], textarea, select{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:var(--glass);color:inherit;font-size:14px}
    textarea{min-height:120px;resize:vertical}
    .profile{background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:12px;border-radius:10px}
    .profile div{font-size:14px}
    .muted{color:var(--muted);font-size:13px}
    .actions{display:flex;gap:8px;margin-top:10px}
    button{background:var(--accent);border:none;padding:10px 12px;border-radius:10px;cursor:pointer;font-weight:600}
    button.ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--muted);font-weight:600}
    .output{margin-top:12px;padding:12px;border-radius:10px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));font-size:14px}
    .block{padding:10px;border-radius:8px;background:rgba(255,255,255,0.01);margin-bottom:10px}
    .label-pill{display:inline-block;padding:6px 8px;border-radius:999px;background:rgba(255,255,255,0.02);font-size:12px;color:var(--muted)}
    footer{margin-top:12px;color:var(--muted);font-size:13px;text-align:center}
    .photo{margin-top:14px;border-radius:12px;overflow:hidden;box-shadow:0 4px 12px rgba(0,0,0,0.4)}
    .photo img{max-width:100%;display:block;border-radius:12px}
  </style>
</head>
<body>
  <div class="wrapper">
    <header>
      <div class="logo">AZ</div>
      <div>
        <h1>Roleplay Swap — Aziz Rahman Widiyanto</h1>
        <p class="lead">Masukkan situasi lalu klik <strong>Mulai Roleplay</strong>. Aplikasi ini akan menghasilkan 2 respons: saat kamu di posisimu (model jadi "dia") dan saat "dia" di posisimu (model jadi "aku").</p>
      </div>
    </header>

    <div class="card">
      <div class="grid">
        <div>
          <div style="display:flex;gap:10px;align-items:flex-start">
            <div class="profile" style="flex:0 0 180px">
              <div><strong>Nama</strong></div>
              <div>Aziz Rahman Widiyanto</div>
              <div style="height:8px"></div>
              <div class="muted">Kelas</div>
              <div>XI TJKT 2</div>
              <div style="height:8px"></div>
              <div class="muted">Absen</div>
              <div>09</div>
            </div>

            <div style="flex:1">
              <label for="situasi">Situasi / konteks</label>
              <textarea id="situasi" placeholder="Contoh: Ujian praktik komputer akan dimulai. Salah satu dari kalian lupa membawa flashdisk..."></textarea>

              <div class="actions">
                <button id="startBtn">Mulai Roleplay</button>
                <button id="swapBtn" class="ghost">Tukar Nama / Edit</button>
                <button id="clearBtn" class="ghost">Bersihkan</button>
              </div>

              <div class="output" id="outputArea" aria-live="polite"></div>

              <div class="photo">
                <img src="IMG-20250906-WA0020.jpg" alt="Foto Aziz di Puncak Kali Talang" />
              </div>
            </div>
          </div>

          <div style="margin-top:12px;display:flex;gap:8px;flex-wrap:wrap">
            <span class="label-pill">Bahasa: Indonesia</span>
            <span class="label-pill">Gaya: Santai namun sopan</span>
            <span class="label-pill">Panjang alasan: 1–2 kalimat</span>
          </div>
        </div>

        <aside class="right">
          <div>
            <label for="roleName">Nama (kamu)</label>
            <input type="text" id="roleName" value="Aziz Rahman Widiyanto">
            <label for="kelas">Kelas</label>
            <input type="text" id="kelas" value="XI TJKT 2">
            <label for="absen">Absen</label>
            <input type="text" id="absen" value="09">

            <div style="margin-top:10px;display:flex;gap:8px">
              <button id="applyBtn" class="ghost">Simpan</button>
              <button id="downloadBtn">Download HTML</button>
            </div>

            <div style="margin-top:12px;color:var(--muted);font-size:13px">Tips: Tulis situasi singkat, lalu klik <strong>Mulai Roleplay</strong>. Kamu bisa edit nama/kelas/absen di panel ini.</div>
          </div>
        </aside>
      </div>

      <footer>Created for <strong>Aziz</strong>. Ingin versi yang lebih tegas, atau tombol untuk ekspor percakapan? Beri tahu aku.</footer>
    </div>
  </div>

  <script>
    const situasiEl = document.getElementById('situasi');
    const outputArea = document.getElementById('outputArea');
    const startBtn = document.getElementById('startBtn');
    const swapBtn = document.getElementById('swapBtn');
    const clearBtn = document.getElementById('clearBtn');
    const roleName = document.getElementById('roleName');
    const kelas = document.getElementById('kelas');
    const absen = document.getElementById('absen');
    const applyBtn = document.getElementById('applyBtn');
    const downloadBtn = document.getElementById('downloadBtn');

    function generateAlasanAksi(context, role) {
      const safeContext = context.trim() || 'Situasi tidak terisi; berikan konteks singkat.';

      if (role === 'dia') {
        const alasan = 'Sebagai "dia", aku ingin membantu supaya situasi tetap tenang dan tugas berjalan.';
        const aksi = `Aku menawarkan solusi praktis yang bisa langsung dilakukan terkait: ${safeContext}`;
        return {alasan, aksi};
      } else {
        const alasan = 'Sebagai "aku", aku merasa bertanggung jawab dan berusaha mencari alternatif cepat.';
        const aksi = `Aku mengecek opsi lain yang tersedia, memberi instruksi singkat, dan menenangkan tim terkait: ${safeContext}`;
        return {alasan, aksi};
      }
    }

    function renderOutput(situasi) {
      const name = roleName.value || 'Aziz Rahman Widiyanto';
      const kelasVal = kelas.value || 'XI TJKT 2';
      const absenVal = absen.value || '09';

      const block1 = generateAlasanAksi(situasi, 'dia');
      const block2 = generateAlasanAksi(situasi, 'aku');

      outputArea.innerHTML = `
        <div class="block">
          <strong>Saat <em>aku</em> ( ${escapeHtml(name)} ) di posisiku — model berperan sebagai "dia"</strong>
          <div style="height:8px"></div>
          <div class="muted">Alasan:</div>
          <div>${escapeHtml(block1.alasan)}</div>
          <div style="height:6px"></div>
          <div class="muted">Aksi:</div>
          <div>${escapeHtml(block1.aksi)}</div>
        </div>

        <div class="block">
          <strong>Saat "dia" di posisimu — model berperan sebagai "aku"</strong>
          <div style="height:8px"></div>
          <div class="muted">Alasan:</div>
          <div>${escapeHtml(block2.alasan)}</div>
          <div style="height:6px"></div>
          <div class="muted">Aksi:</div>
          <div>${escapeHtml(block2.aksi)}</div>
        </div>

        <div class="muted" style="font-size:12px">Profil: ${escapeHtml(name)} • ${escapeHtml(kelasVal)} • Absen ${escapeHtml(absenVal)}</div>
      `;
    }

    function escapeHtml(text){
      return String(text)
        .replace(/&/g, '&amp;')
        .replace(/</g, '&lt;')
        .replace(/>/g, '&gt;')
        .replace(/\"/g, '&quot;')
        .replace(/'/g, '&#039;');
    }

    startBtn.addEventListener('click', ()=>{
      renderOutput(situasiEl.value);
    });

    clearBtn.addEventListener('click', ()=>{
      situasiEl.value = '';
      outputArea.innerHTML = '';
    });

    swapBtn.addEventListener('click', ()=>{
      const current = roleName.value || '';
      roleName.value = current === 'Dia' ? 'Aziz Rahman Widiyanto' : 'Dia';
    });

    applyBtn.addEventListener('click', ()=>{
      applyBtn.textContent = 'Tersimpan ✓';
      setTimeout(()=> applyBtn.textContent = 'Simpan', 1200);
    });

    downloadBtn.addEventListener('click', ()=>{
      const html = '<!doctype html>\n' + document.documentElement.outerHTML;
      const blob = new Blob([html], {type: 'text/html'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url;
      a.download = 'roleplay_aziz.html';
      document.body.appendChild(a);
      a.click();
      a.remove();
      URL.revokeObjectURL(url);
    });

    situasiEl.addEventListener('keydown', (e)=>{
      if ((e.ctrlKey || e.metaKey) && e.key === 'Enter') {
        e.preventDefault();
        startBtn.click();
      }
    });
  </script>
</body>
</html>
