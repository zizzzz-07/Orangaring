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
