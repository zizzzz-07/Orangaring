#orangaring
pemula......
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Profil Aziz</title>
  <style>
    :root{
      --bg: #e6f7ff;
      --card: #0b3b5e;
      --accent: #60a5fa;
      --text: #04293a;
    }
    body{
      margin:0;
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      background:linear-gradient(180deg,#f0f9ff 0%, #e6f7ff 100%);
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      color:var(--text);
    }
    .card{
      width:320px;
      padding:22px;
      border-radius:14px;
      background: white;
      box-shadow: 0 8px 30px rgba(3,10,18,0.12);
      text-align:center;
    }
    h1{margin:0 0 8px;font-size:20px;color:var(--card)}
    .meta{color:#274c5b;margin:6px 0;font-weight:600}
    .cool{margin-top:14px;background:linear-gradient(90deg,#dbefff,#cfefff);padding:10px;border-radius:10px;font-weight:700;color:#05445e}
    .small{font-size:13px;color:#5b7785;margin-top:6px}
    button.copyBtn{
      margin-top:12px;
      padding:8px 12px;
      border-radius:9px;
      border:none;
      background:var(--accent);
      color:white;
      cursor:pointer;
      font-weight:600;
    }
  </style>
</head>
<body>
  <div class="card" role="region" aria-label="Profil Aziz">
    <h1>Profil Sederhana</h1>

    <div class="meta">Nama : <strong>Aziz Rahman W</strong></div>
    <div class="meta">Kelas : <strong>XI TJKT 2</strong></div>
    <div class="meta">Absen : <strong>09</strong></div>

    <div class="cool">Dingin abiezzzz</div>
    <div class="small">(Tekan tombol untuk menyalin teks)</div>

    <button class="copyBtn" id="copyBtn">Salin Profil</button>
  </div>

  <script>
    const textToCopy = `Nama : Aziz Rahman W
Kelas : XI TJKT 2
Absen : 09
Dingin abiezzzz`;

    document.getElementById('copyBtn').addEventListener('click', async () => {
      try {
        await navigator.clipboard.writeText(textToCopy);
        document.getElementById('copyBtn').textContent = 'Tersalin ✓';
        setTimeout(()=> document.getElementById('copyBtn').textContent = 'Salin Profil', 1400);
      } catch (e) {
        alert('Gagal menyalin. Kamu bisa blok teks dan tekan Ctrl+C / Cmd+C.');
      }
    });
  </script>
</body>
</html>
