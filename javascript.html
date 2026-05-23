/* ─────────────────────────────────────────
   SMART SMAN 2 Sampit — Global JS Utilities
   ───────────────────────────────────────── */

// ── Tab switching ──────────────────────────────────────
function initTabs(containerSelector) {
  const containers = document.querySelectorAll(containerSelector || '[data-tabs]');
  containers.forEach(container => {
    const btns   = container.querySelectorAll('.tab-btn');
    const panels = container.querySelectorAll('.tab-panel');
    btns.forEach((btn, i) => {
      btn.addEventListener('click', () => {
        btns.forEach(b => b.classList.remove('active'));
        panels.forEach(p => p.classList.remove('active'));
        btn.classList.add('active');
        if (panels[i]) panels[i].classList.add('active');
      });
    });
    // activate first by default
    if (btns[0])   btns[0].classList.add('active');
    if (panels[0]) panels[0].classList.add('active');
  });
}

// ── Active nav item ────────────────────────────────────
function initNavActive() {
  const page = location.pathname.split('/').pop() || 'index.html';
  document.querySelectorAll('.nav-item').forEach(item => {
    const href = item.getAttribute('href') || '';
    if (href === page) item.classList.add('active');
    item.addEventListener('click', function () {
      document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
      this.classList.add('active');
    });
  });
}

// ── Toast notification ─────────────────────────────────
function showToast(msg, type = 'success') {
  let toast = document.getElementById('smart-toast');
  if (!toast) {
    toast = document.createElement('div');
    toast.id = 'smart-toast';
    toast.style.cssText = `
      position:fixed;bottom:24px;right:24px;z-index:9999;
      padding:12px 20px;border-radius:10px;font-family:'Plus Jakarta Sans',sans-serif;
      font-size:13px;font-weight:600;box-shadow:0 4px 16px rgba(0,0,0,.15);
      transition:opacity .3s;opacity:0;pointer-events:none;max-width:360px;line-height:1.4;
    `;
    document.body.appendChild(toast);
  }
  const colors = {
    success: 'background:#ecfdf5;color:#065f46;border:1px solid #a7f3d0',
    error:   'background:#fef2f2;color:#991b1b;border:1px solid #fecaca',
    warning: 'background:#fffbeb;color:#92400e;border:1px solid #fde68a',
    info:    'background:#eff6ff;color:#1e40af;border:1px solid #bfdbfe',
  };
  toast.style.cssText += colors[type] || colors.success;
  toast.textContent = msg;
  toast.style.opacity = '1';
  setTimeout(() => { toast.style.opacity = '0'; }, 3000);
}

// ── Confirm dialog ─────────────────────────────────────
function confirmAction(msg, callback) {
  if (window.confirm(msg)) callback();
}

// ── Format date ────────────────────────────────────────
function formatDate(dateStr) {
  const days   = ['Minggu','Senin','Selasa','Rabu','Kamis','Jumat','Sabtu'];
  const months = ['Januari','Februari','Maret','April','Mei','Juni',
                  'Juli','Agustus','September','Oktober','November','Desember'];
  const d = new Date(dateStr);
  return `${days[d.getDay()]}, ${d.getDate()} ${months[d.getMonth()]} ${d.getFullYear()}`;
}

// ── Today's date display ───────────────────────────────
function setTodayDate(selector) {
  const el = document.querySelector(selector);
  if (el) el.textContent = formatDate(new Date().toISOString().slice(0,10));
}

// ── Animate progress bars ──────────────────────────────
function animateProgressBars() {
  document.querySelectorAll('.prog-fill[data-pct]').forEach(bar => {
    const pct = bar.getAttribute('data-pct');
    setTimeout(() => { bar.style.width = pct + '%'; }, 100);
  });
}

// ── Counter animation ──────────────────────────────────
function animateCounters() {
  document.querySelectorAll('[data-count]').forEach(el => {
    const target = parseInt(el.getAttribute('data-count'));
    let current = 0;
    const step = Math.ceil(target / 40);
    const timer = setInterval(() => {
      current = Math.min(current + step, target);
      el.textContent = current.toLocaleString('id-ID');
      if (current >= target) clearInterval(timer);
    }, 20);
  });
}

// ── Export table to CSV ────────────────────────────────
function exportTableCSV(tableId, filename) {
  const table = document.getElementById(tableId);
  if (!table) return;
  const rows = Array.from(table.querySelectorAll('tr'));
  const csv  = rows.map(r =>
    Array.from(r.querySelectorAll('th,td'))
      .map(c => `"${c.innerText.replace(/"/g,'""')}"`)
      .join(',')
  ).join('\n');
  const blob = new Blob(['\uFEFF' + csv], { type: 'text/csv;charset=utf-8;' });
  const url  = URL.createObjectURL(blob);
  const a    = document.createElement('a');
  a.href = url; a.download = filename || 'export.csv'; a.click();
  URL.revokeObjectURL(url);
  showToast('✅ Data berhasil diexport sebagai CSV');
}

// ── Print page ─────────────────────────────────────────
function printPage() { window.print(); }

// ── Search / filter table rows ─────────────────────────
function filterTable(inputId, tableId, colIndex) {
  const input = document.getElementById(inputId);
  const table = document.getElementById(tableId);
  if (!input || !table) return;
  input.addEventListener('input', () => {
    const val = input.value.toLowerCase();
    table.querySelectorAll('tbody tr').forEach(row => {
      const cell = row.cells[colIndex !== undefined ? colIndex : 0];
      row.style.display = cell && cell.textContent.toLowerCase().includes(val) ? '' : 'none';
    });
  });
}

// ── Signature pad ──────────────────────────────────────
function initSignaturePad(canvasId, hintId) {
  const canvas = document.getElementById(canvasId);
  if (!canvas) return null;
  const ctx = canvas.getContext('2d');
  ctx.strokeStyle = '#1a56db'; ctx.lineWidth = 2; ctx.lineCap = 'round'; ctx.lineJoin = 'round';
  let drawing = false, hasSig = false;
  function pos(e) {
    const r = canvas.getBoundingClientRect();
    const src = e.touches ? e.touches[0] : e;
    return [src.clientX - r.left, src.clientY - r.top];
  }
  canvas.addEventListener('mousedown',  e => { drawing = true; ctx.beginPath(); ctx.moveTo(...pos(e)); });
  canvas.addEventListener('touchstart', e => { e.preventDefault(); drawing = true; ctx.beginPath(); ctx.moveTo(...pos(e)); }, {passive:false});
  canvas.addEventListener('mousemove',  e => { if (!drawing) return; ctx.lineTo(...pos(e)); ctx.stroke(); hasSig = true; if (hintId) document.getElementById(hintId)?.classList.add('hidden'); });
  canvas.addEventListener('touchmove',  e => { e.preventDefault(); if (!drawing) return; ctx.lineTo(...pos(e)); ctx.stroke(); hasSig = true; if (hintId) document.getElementById(hintId)?.classList.add('hidden'); }, {passive:false});
  canvas.addEventListener('mouseup',    () => drawing = false);
  canvas.addEventListener('touchend',   () => drawing = false);
  canvas.addEventListener('mouseleave', () => drawing = false);
  return {
    clear() { ctx.clearRect(0, 0, canvas.width, canvas.height); hasSig = false; if (hintId) document.getElementById(hintId)?.classList.remove('hidden'); },
    isEmpty() { return !hasSig; },
    toDataURL() { return canvas.toDataURL(); }
  };
}

// ── Mobile sidebar toggle ──────────────────────────────
function initMobileSidebar() {
  const sidebar = document.querySelector('.sidebar');
  const toggle  = document.querySelector('.btn-menu-toggle');
  if (!sidebar || !toggle) return;
  toggle.addEventListener('click', () => sidebar.classList.toggle('open'));
  document.addEventListener('click', e => {
    if (!sidebar.contains(e.target) && !toggle.contains(e.target)) sidebar.classList.remove('open');
  });
}

// ── Init all on DOM ready ──────────────────────────────
document.addEventListener('DOMContentLoaded', () => {
  initTabs();
  initNavActive();
  animateProgressBars();
  animateCounters();
  initMobileSidebar();
  setTodayDate('.today-date');
});
