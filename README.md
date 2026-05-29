
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kurir Supra</title>
<link href="https://fonts.googleapis.com/css2?family=Goldman:wght@400;700&display=swap" rel="stylesheet">
<style>
:root{
  --tosca:#14b8a6;
  --tosca-dark:#0d9488;
  --tosca-light:#ccfbf1;
  --danger:#ef4444;
  --gray-100:#f3f4f6;
  --gray-200:#e5e7eb;
  --gray-500:#6b7280;
  --gray-700:#374151;
}
*{margin:0;padding:0;box-sizing:border-box;font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,sans-serif}
body{background:#f9fafb;padding-bottom:70px}

.header{position:fixed;top:0;left:0;right:0;background:var(--tosca);color:#fff;padding:12px 16px;z-index:50;box-shadow:0 2px 8px rgba(0,0,0,0.1)}
.header-top{display:flex;justify-content:space-between;align-items:center}
.header-title{font-family:'Goldman',sans-serif;font-size:20px;font-weight:700}
.header-desc{font-size:11px;opacity:0.9;margin-top:2px}
.status-badge{font-size:12px;padding:6px 12px;border-radius:20px;font-weight:600}
.status-online{background:#fff;color:var(--tosca)}
.status-offline{background:#fee2e2;color:#dc2626}

.content{margin-top:80px;padding:16px}
.banner{border-radius:12px;overflow:hidden;margin-bottom:16px;position:relative;height:140px;background:var(--tosca-light)}
.banner-slide{display:none;width:100%;height:100%;object-fit:cover}
.banner-slide.active{display:block}
.banner-dots{position:absolute;bottom:8px;left:0;right:0;display:flex;justify-content:center;gap:6px}
.dot{width:6px;height:6px;border-radius:50%;background:rgba(255,255,255,0.5)}
.dot.active{background:#fff}

.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-bottom:20px}
.grid-item{background:#fff;border-radius:12px;padding:16px 8px;text-align:center;cursor:pointer;box-shadow:0 1px 3px rgba(0,0,0,0.08)}
.grid-item:active{transform:scale(0.95)}
.grid-icon{width:40px;height:40px;background:var(--tosca-light);border-radius:10px;display:flex;align-items:center;justify-content:center;margin:0 auto 8px;color:var(--tosca);font-size:20px}
.grid-item p{font-size:12px;font-weight:600;color:var(--gray-700)}

.footer{position:fixed;bottom:0;left:0;right:0;background:#fff;border-top:1px solid var(--gray-200);display:flex;justify-content:space-around;padding:8px 0;max-width:480px;margin:0 auto}
.nav-item{text-align:center;font-size:11px;color:var(--gray-500);cursor:pointer;padding:6px 12px}
.nav-item.active{color:var(--tosca)}
.nav-item svg{width:24px;height:24px;margin:0 auto 2px;display:block}

.modal{display:none;position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.5);z-index:100;align-items:flex-end;justify-content:center}
.modal.active{display:flex}
.modal-content{background:#fff;width:100%;max-width:480px;border-radius:20px 20px 0 0;padding:20px;max-height:85vh;overflow-y:auto}
.form-group{margin-bottom:12px}
.form-group label{display:block;font-size:13px;color:var(--gray-700);margin-bottom:6px;font-weight:600}
.input,textarea,select{width:100%;padding:10px 12px;border:1px solid var(--gray-200);border-radius:8px;font-size:14px}
.input:focus,textarea:focus,select:focus{outline:none;border-color:var(--tosca)}
textarea{resize:none;height:60px}
.btn{padding:12px 16px;border-radius:8px;border:none;background:var(--tosca);color:#fff;font-weight:600;width:100%;cursor:pointer}
.btn-secondary{background:var(--gray-200);color:var(--gray-700)}

.page{display:none}
.page.active{display:block}
.card{background:#fff;border-radius:12px;padding:14px;margin-bottom:12px;box-shadow:0 1px 3px rgba(0,0,0,0.08)}
.badge{padding:4px 10px;border-radius:12px;font-size:12px;background:var(--tosca-light);color:var(--tosca-dark);font-weight:600}
.hidden{display:none}
</style>
</head>
<body>

<!-- HEADER FIXED -->
<div class="header">
  <div class="header-top">
    <div>
      <div class="header-title">Kurir Supra</div>
      <div class="header-desc">Kurir Aman, Nyaman, Dan Amanah</div>
    </div>
    <div id="statusText">
      <span class="status-badge status-offline">Offline</span>
    </div>
  </div>
</div>

<!-- CONTENT -->
<div class="content">

  <!-- PAGE HOME -->
  <div class="page active" id="page-home">
    <div class="banner">
      <img src="https://drive.google.com/thumbnail?id=1t3TRBJthZ_9cFutnnKtRiYG_tJ5REdib&sz=w1000" class="banner-slide active">
      <img src="https://drive.google.com/thumbnail?id=1mj6eeAfv9a_nhLBzzJYs64BgTCJN2-eC&sz=w1000" class="banner-slide">
      <div class="banner-dots">
        <span class="dot active"></span>
        <span class="dot"></span>
      </div>
    </div>

    <div class="grid">
      <div class="grid-item" onclick="openModal('modal-belikan')"><div class="grid-icon">🛍️</div><p>Belikan</p></div>
      <div class="grid-item" onclick="openModal('modal-ambil')"><div class="grid-icon">📦</div><p>Ambilkan Pesanan</p></div>
      <div class="grid-item" onclick="openModal('modal-antar')"><div class="grid-icon">🚚</div><p>Antarkan</p></div>
      <div class="grid-item" onclick="openModal('modal-ojek')"><div class="grid-icon">🏍️</div><p>Ojek</p></div>
      <div class="grid-item" onclick="openModal('modal-belanja')"><div class="grid-icon">🛒</div><p>Belanjaan</p></div>
      <div class="grid-item" onclick="openModal('modal-undangan')"><div class="grid-icon">💌</div><p>Undangan Digital</p></div>
    </div>
  </div>

  <!-- PAGE NOTA -->
  <div class="page" id="page-nota">
    <h3 style="margin-bottom:12px">Nota Digital</h3>
    <div class="form-group">
      <label>No WA Pelanggan</label>
      <input type="tel" class="input" id="notaWA" placeholder="08xxxxxxxxxx" value="08">
    </div>
    <div id="notaItems"></div>
    <button class="btn btn-secondary" onclick="tambahItemNota()">+ Tambah Barang</button>
    <div style="margin:16px 0">
      <div class="form-group">
        <label>Ongkir</label>
        <input type="number" class="input" id="notaOngkir" value="10000" oninput="hitungTotalNota()">
      </div>
      <div style="display:flex;justify-content:space-between;font-weight:700;font-size:18px;margin-top:12px;padding:12px;background:var(--tosca-light);border-radius:8px">
        <span>Total:</span>
        <span id="notaTotal">Rp0</span>
      </div>
    </div>
    <button class="btn" onclick="kirimNotaWA()">Kirim Nota ke WA Pelanggan</button>
  </div>

  <!-- PAGE RIWAYAT -->
  <div class="page" id="page-riwayat">
    <h3 style="margin-bottom:12px">Riwayat Order</h3>
    <div id="riwayatList"></div>
  </div>

  <!-- PAGE AKUN -->
  <div class="page" id="page-akun">
    <h3 style="margin-bottom:12px">Data Akun</h3>
    <div class="card">
      <div class="form-group"><label>Nama</label><input type="text" class="input" id="akunNama" oninput="saveAkun()"></div>
      <div class="form-group"><label>Alamat</label><textarea class="input" id="akunAlamat" oninput="saveAkun()"></textarea></div>
      <div class="form-group"><label>No WhatsApp</label><input type="tel" class="input" id="akunWA" oninput="saveAkun()"></div>
      <span class="badge">Auto Save ke Browser</span>
    </div>
  </div>
</div>

<!-- FOOTER NAV -->
<div class="footer">
  <div class="nav-item active" onclick="showPage('home')"><svg fill="currentColor" viewBox="0 0 20 20"><path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z"/></svg>Home</div>
  <div class="nav-item" onclick="showPage('riwayat')"><svg fill="currentColor" viewBox="0 0 20 20"><path d="M4 3a2 2 0 100 4h12a2 2 0 100-4H4zM3 8h14v7a2 2 0 01-2 2H5a2 2 0 01-2-2V8z"/></svg>Riwayat</div>
  <div class="nav-item" onclick="showPage('nota')"><svg fill="currentColor" viewBox="0 0 20 20"><path d="M9 2a1 1 0 000 2h2a1 1 0 100-2H9zM4 5a2 2 0 012-2 3 3 0 003 3h2a3 3 0 003-3 2 2 0 012 2v11a2 2 0 01-2 2H6a2 2 0 01-2-2V5z"/></svg>Nota</div>
  <div class="nav-item" onclick="showPage('akun')"><svg fill="currentColor" viewBox="0 0 20 20"><path d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z"/></svg>Akun</div>
</div>

<!-- MODAL UNDANGAN DIGITAL DENGAN FORM DINAMIS -->
<div class="modal" id="modal-undangan">
  <div class="modal-content">
    <h3>Buat Undangan Digital</h3>

    <div class="form-group">
      <label>Jenis Undangan</label>
      <select class="input" id="jenisUndangan" onchange="gantiFormUndangan()">
        <option value="pernikahan">Undangan Pernikahan</option>
        <option value="tasmiah">Undangan Tasmiah</option>
        <option value="haji">Undangan Haji dan Umroh</option>
        <option value="ultah">Undangan Ulang Tahun</option>
        <option value="khitan">Undangan Syukuran Khitanan</option>
        <option value="maulid">Undangan Maulid Nabi</option>
        <option value="isra">Undangan Isra' Mi'raj</option>
        <option value="haul">Undangan Haul/Tahlil</option>
      </select>
    </div>

    <!-- FORM PERNIKAHAN -->
    <div id="form-pernikahan" class="form-undangan">
      <div class="form-group"><label>Nama Mempelai Pria</label><input type="text" class="input" id="namaPria" placeholder="Contoh: Ahmad"></div>
      <div class="form-group"><label>Nama Mempelai Wanita</label><input type="text" class="input" id="namaWanita" placeholder="Contoh: Siti"></div>
      <div class="form-group"><label>Nama Orang Tua Pria</label><input type="text" class="input" id="ortuPria" placeholder="Bpk. & Ibu."></div>
      <div class="form-group"><label>Nama Orang Tua Wanita</label><input type="text" class="input" id="ortuWanita" placeholder="Bpk. & Ibu."></div>
    </div>

    <!-- FORM TASMIAH -->
    <div id="form-tasmiah" class="form-undangan hidden">
      <div class="form-group"><label>Nama Bayi</label><input type="text" class="input" id="namaBayi" placeholder="Contoh: Muhammad Ali"></div>
      <div class="form-group"><label>Nama Orang Tua</label><input type="text" class="input" id="ortuBayi" placeholder="Bpk. & Ibu."></div>
      <div class="form-group"><label>Jenis Kelamin</label>
        <select class="input" id="jkBayi"><option value="Putra">Putra</option><option value="Putri">Putri</option></select>
      </div>
    </div>

    <!-- FORM HAJI UMROH -->
    <div id="form-haji" class="form-undangan hidden">
      <div class="form-group"><label>Nama Jamaah</label><input type="text" class="input" id="namaJamaah" placeholder="Contoh: H. Ahmad"></div>
      <div class="form-group"><label>Tujuan</label>
        <select class="input" id="tujuanHaji"><option value="Haji">Ibadah Haji</option><option value="Umroh">Umroh</option></select>
      </div>
    </div>

    <!-- FORM ULANG TAHUN -->
    <div id="form-ultah" class="form-undangan hidden">
      <div class="form-group"><label>Nama</label><input type="text" class="input" id="namaUltah" placeholder="Contoh: Dinda"></div>
      <div class="form-group"><label>Usia ke</label><input type="number" class="input" id="usiaUltah" placeholder="Contoh: 17"></div>
    </div>

    <!-- FORM KHITAN -->
    <div id="form-khitan" class="form-undangan hidden">
      <div class="form-group"><label>Nama Anak</label><input type="text" class="input" id="namaKhitan" placeholder="Contoh: Rizki"></div>
      <div class="form-group"><label>Nama Orang Tua</label><input type="text" class="input" id="ortuKhitan" placeholder="Bpk. & Ibu."></div>
    </div>

    <!-- FORM MAULID -->
    <div id="form-maulid" class="form-undangan hidden">
      <div class="form-group"><label>Tema Acara</label><input type="text" class="input" id="temaMaulid" placeholder="Contoh: Meneladani Akhlak Rasulullah"></div>
      <div class="form-group"><label>Penceramah</label><input type="text" class="input" id="penceramahMaulid" placeholder="Ustadz/Dr."></div>
    </div>

    <!-- FORM ISRA MI'RAJ -->
    <div id="form-isra" class="form-undangan hidden">
      <div class="form-group"><label>Tema Acara</label><input type="text" class="input" id="temaIsra" placeholder="Contoh: Hikmah Isra Mi'raj"></div>
      <div class="form-group"><label>Penceramah</label><input type="text" class="input" id="penceramahIsra" placeholder="Ustadz/Dr."></div>
    </div>

    <!-- FORM HAUL -->
    <div id="form-haul" class="form-undangan hidden">
      <div class="form-group"><label>Nama Almarhum/Almarhumah</label><input type="text" class="input" id="namaAlmarhum" placeholder="Contoh: H. Ahmad bin Sulaiman"></div>
      <div class="form-group"><label>Haul ke</label><input type="number" class="input" id="haulKe" placeholder="Contoh: 1"></div>
    </div>

    <!-- FORM UMUM UNTUK SEMUA JENIS -->
    <div class="form-group"><label>Tanggal Acara</label><input type="date" class="input" id="tanggalUndangan"></div>
    <div class="form-group"><label>Jam Acara</label><input type="time" class="input" id="jamUndangan"></div>
    <div class="form-group"><label>Tempat Acara</label><textarea class="input" id="tempatUndangan" placeholder="Alamat lengkap"></textarea></div>
    <div class="form-group"><label>No WA Teman</label><input type="tel" class="input" id="waTeman" placeholder="08xxxxxxxxxx"></div>
    <div class="form-group"><label>Ucapan Tambahan</label><textarea class="input" id="ucapanUndangan" placeholder="Opsional"></textarea></div>

    <button class="btn" onclick="kirimUndanganWA()">Kirim Undangan via WhatsApp</button>
    <button class="btn btn-secondary" style="margin-top:8px" onclick="closeModal()">Batal</button>
  </div>
</div>

<!-- MODAL LAINNYA TETAP -->
<div class="modal" id="modal-belikan"><div class="modal-content"><h3>Beli Barang</h3><div class="form-group"><label>Beli Apa?</label><input type="text" class="input" id="beliApa"></div><div class="form-group"><label>Beli Dimana?</label><input type="text" class="input" id="beliDimana"></div><div class="form-group"><label>Catatan</label><textarea class="input" id="beliCatatan"></textarea></div><button class="btn" onclick="kirimOrder('Belikan')">Kirim Order</button><button class="btn btn-secondary" style="margin-top:8px" onclick="closeModal()">Batal</button></div></div>
<div class="modal" id="modal-ambil"><div class="modal-content"><h3>Ambil Pesanan</h3><div class="form-group"><label>Ambil Dimana?</label><input type="text" class="input" id="ambilDimana"></div><div class="form-group"><label>Keterangan</label><input type="text" class="input" id="ambilKeterangan"></div><div class="form-group"><label>WA Penjual</label><input type="tel" class="input" id="ambilWA"></div><button class="btn" onclick="kirimOrder('Ambil Pesanan')">Kirim Order</button><button class="btn btn-secondary" style="margin-top:8px" onclick="closeModal()">Batal</button></div></div>
<div class="modal" id="modal-antar"><div class="modal-content"><h3>Antar Barang</h3><div class="form-group"><label>Nama Penerima</label><input type="text" class="input" id="antarNama"></div><div class="form-group"><label>Alamat</label><textarea class="input" id="antarAlamat"></textarea></div><div class="form-group"><label>WA Penerima</label><input type="tel" class="input" id="antarWA"></div><div class="form-group"><label>Keterangan</label><input type="text" class="input" id="antarKeterangan"></div><button class="btn" onclick="kirimOrder('Antar Barang')">Kirim Order</button><button class="btn btn-secondary" style="margin-top:8px" onclick="closeModal()">Batal</button></div></div>
<div class="modal" id="modal-ojek"><div class="modal-content"><h3>Ojek Online</h3><div class="form-group"><label>Jemput Dimana?</label><input type="text" class="input" id="ojekJemput"></div><div class="form-group"><label>Tujuan</label><input type="text" class="input" id="ojekTujuan"></div><div class="form-group"><label>WA Order</label><input type="tel" class="input" id="ojekWA"></div><button class="btn" onclick="kirimOrder('Ojek')">Kirim Order</button><button class="btn btn-secondary" style="margin-top:8px" onclick="closeModal()">Batal</button></div></div>
<div class="modal" id="modal-belanja"><div class="modal-content"><h3>Belanjaan</h3><div class="form-group"><label>Beli Dimana?</label><input type="text" class="input" id="belanjaDimana"></div><div id="belanjaList"></div><button class="btn btn-secondary" onclick="tambahBelanja()">+ Tambah Item</button><button class="btn" style="margin-top:12px" onclick="kirimOrder('Belanjaan')">Kirim Order</button><button class="btn btn-secondary" style="margin-top:8px" onclick="closeModal()">Batal</button></div></div>

<script>
const NO_WA = "6283137527300";
let riwayat = JSON.parse(localStorage.getItem('kurir_riwayat')) || [];
let akun = JSON.parse(localStorage.getItem('kurir_akun')) || {nama:'',alamat:'',wa:''};

// INIT
loadAkun();
renderRiwayat();
renderNota();
cekJamOperasional();
setInterval(cekJamOperasional, 60000);
slideBanner();
gantiFormUndangan();

// CEK APAKAH ONLINE - PAKAI JAM WITA UTC+8 JAM 08:00-17:00
function isOnline(){
  const now = new Date();
  const utc = now.getTime() + (now.getTimezoneOffset() * 60000);
  const wita = new Date(utc + (3600000 * 8));
  const hour = wita.getHours();
  return hour >= 8 && hour < 21; // 17:00 WITA tutup
}

// STATUS ONLINE/OFFLINE - TAMPILKAN JAM WITA
function cekJamOperasional(){
  const now = new Date();
  const utc = now.getTime() + (now.getTimezoneOffset() * 60000);
  const wita = new Date(utc + (3600000 * 8));
  const hour = wita.getHours();
  const menit = wita.getMinutes();
  const statusText = document.getElementById('statusText');

  if(hour >= 8 && hour < 21){
    statusText.innerHTML = `<span class="status-badge status-online">Online - ${hour}:${menit.toString().padStart(2,'0')} WITA</span>`;
  }else{
    statusText.innerHTML = `<span class="status-badge status-offline">Offline - ${hour}:${menit.toString().padStart(2,'0')} WITA</span>`;
  }
}

// BANNER SLIDE
let currentSlide = 0;
function slideBanner(){
  const slides = document.querySelectorAll('.banner-slide');
  const dots = document.querySelectorAll('.dot');
  setInterval(()=>{
    slides[currentSlide].classList.remove('active');
    dots[currentSlide].classList.remove('active');
    currentSlide = (currentSlide + 1) % slides.length;
    slides[currentSlide].classList.add('active');
    dots[currentSlide].classList.add('active');
  }, 3000);
}

// NAVIGASI
function showPage(page){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.getElementById('page-'+page).classList.add('active');
  document.querySelectorAll('.nav-item').forEach(n=>n.classList.remove('active'));
  event.target.closest('.nav-item').classList.add('active');
  if(page=='nota') hitungTotalNota();
}

// MODAL
function openModal(id){
  document.getElementById(id).classList.add('active');
}
function closeModal(){
  document.querySelectorAll('.modal').forEach(m=>m.classList.remove('active'));
}

// GANTI FORM UNDANGAN SESUAI JENIS
function gantiFormUndangan(){
  const jenis = document.getElementById('jenisUndangan').value;
  document.querySelectorAll('.form-undangan').forEach(f=>f.classList.add('hidden'));
  document.getElementById('form-'+jenis).classList.remove('hidden');
}

// KIRIM ORDER KE WA KURIR - HANYA 1 FUNGSI DENGAN CEK ONLINE
function kirimOrder(jenis){
  if(!isOnline()){
    alert('Maaf, saat ini Kurir Supra sedang Offline. Jam operasional 08:00-17:00 WITA');
    return;
  }

  let pesan = `*Order Kurir Supra*%0A`;
  pesan += `Jenis: ${jenis}%0A%0A`;

  if(jenis=='Belikan'){
    pesan += `Beli Apa: ${document.getElementById('beliApa').value}%0A`;
    pesan += `Beli Dimana: ${document.getElementById('beliDimana').value}%0A`;
    pesan += `Catatan: ${document.getElementById('beliCatatan').value}`;
  }
  if(jenis=='Ambil Pesanan'){
    pesan += `Ambil Dimana: ${document.getElementById('ambilDimana').value}%0A`;
    pesan += `Keterangan: ${document.getElementById('ambilKeterangan').value}%0A`;
    pesan += `WA Penjual: ${document.getElementById('ambilWA').value}`;
  }
  if(jenis=='Antar Barang'){
    pesan += `Nama Penerima: ${document.getElementById('antarNama').value}%0A`;
    pesan += `Alamat: ${document.getElementById('antarAlamat').value}%0A`;
    pesan += `WA Penerima: ${document.getElementById('antarWA').value}%0A`;
    pesan += `Keterangan: ${document.getElementById('antarKeterangan').value}`;
  }
  if(jenis=='Ojek'){
    pesan += `Jemput: ${document.getElementById('ojekJemput').value}%0A`;
    pesan += `Tujuan: ${document.getElementById('ojekTujuan').value}%0A`;
    pesan += `WA Order: ${document.getElementById('ojekWA').value}`;
  }
  if(jenis=='Belanjaan'){
    pesan += `Beli Dimana: ${document.getElementById('belanjaDimana').value}%0A`;
    pesan += `List Belanjaan:%0A`;
    for(let i=1;i<=10;i++){
      const el = document.getElementById('belanja'+i);
      if(el && el.value) pesan += `${i}. ${el.value}%0A`;
    }
  }

  riwayat.unshift({
    id:Date.now(),
    jenis,
    detail:pesan.replace(/\*|\%0A/g,' '),
    tanggal:new Date().toLocaleString('id-ID')
  });
  localStorage.setItem('kurir_riwayat',JSON.stringify(riwayat));
  renderRiwayat();

  window.open(`https://wa.me/${NO_WA}?text=${pesan}`,'_blank');
  alert('Order terkirim ke WhatsApp Kurir!');
  closeModal();
}

// KIRIM UNDANGAN DIGITAL - DENGAN CEK ONLINE
function kirimUndanganWA(){
  if(!isOnline()){
    alert('Maaf, fitur kirim undangan hanya aktif jam 08:00-17:00 WITA');
    return;
  }

  const jenis = document.getElementById('jenisUndangan').value;
  const tanggal = document.getElementById('tanggalUndangan').value;
  const jam = document.getElementById('jamUndangan').value;
  const tempat = document.getElementById('tempatUndangan').value;
  const waTeman = document.getElementById('waTeman').value.replace(/[^0-9]/g,'');
  const ucapan = document.getElementById('ucapanUndangan').value;

  if(!tanggal ||!jam ||!tempat ||!waTeman){
    alert('Lengkapi tanggal, jam, tempat, dan no WA!');
    return;
  }

  const tanggalFormat = new Date(tanggal).toLocaleDateString('id-ID', {weekday:'long', year:'numeric', month:'long', day:'numeric'});
  let pesan = '';
  let judul = '';

  if(jenis=='pernikahan'){
    const pria = document.getElementById('namaPria').value;
    const wanita = document.getElementById('namaWanita').value;
    const ortuPria = document.getElementById('ortuPria').value;
    const ortuWanita = document.getElementById('ortuWanita').value;
    judul = 'UNDANGAN PERNIKAHAN';
    pesan = `*${judul}*%0A%0A`;
    pesan += `Dengan memohon rahmat dan ridho Allah SWT, kami bermaksud mengundang Bapak/Ibu/Saudara/i untuk hadir pada acara pernikahan putra-putri kami:%0A%0A`;
    pesan += `*${pria}*%0A`;
    pesan += `Putra dari ${ortuPria}%0A%0A`;
    pesan += `*DAN*%0A%0A`;
    pesan += `*${wanita}*%0A`;
    pesan += `Putri dari ${ortuWanita}%0A%0A`;
  }

  if(jenis=='tasmiah'){
    const namaBayi = document.getElementById('namaBayi').value;
    const ortuBayi = document.getElementById('ortuBayi').value;
    const jk = document.getElementById('jkBayi').value;
    judul = 'UNDANGAN TASMIAH';
    pesan = `*${judul}*%0A%0A`;
    pesan += `Alhamdulillah, dengan penuh syukur kami mengundang Bapak/Ibu/Saudara/i untuk hadir pada acara tasmiah dan aqiqah putra/putri kami:%0A%0A`;
    pesan += `*${namaBayi}*%0A`;
    pesan += `${jk} dari ${ortuBayi}%0A%0A`;
  }

  if(jenis=='haji'){
    const namaJamaah = document.getElementById('namaJamaah').value;
    const tujuan = document.getElementById('tujuanHaji').value;
    judul = `UNDANGAN ${tujuan.toUpperCase()}`;
    pesan = `*${judul}*%0A%0A`;
    pesan += `Alhamdulillah, dengan mengharap ridho Allah SWT, kami sekeluarga mengundang Bapak/Ibu/Saudara/i untuk menghadiri acara pelepasan keberangkatan ${tujuan}:%0A%0A`;
    pesan += `*${namaJamaah}*%0A%0A`;
  }

  if(jenis=='ultah'){
    const nama = document.getElementById('namaUltah').value;
    const usia = document.getElementById('usiaUltah').value;
    judul = 'UNDANGAN ULANG TAHUN';
    pesan = `*${judul}*%0A%0A`;
    pesan += `Yuk hadir dan rayakan ulang tahun ${nama} yang ke-${usia} bersama kami!%0A%0A`;
  }

  if(jenis=='khitan'){
    const namaAnak = document.getElementById('namaKhitan').value;
    const ortu = document.getElementById('ortuKhitan').value;
    judul = 'UNDANGAN SYUKURAN KHITAN';
    pesan = `*${judul}*%0A%0A`;
    pesan += `Dengan memanjatkan puji syukur kehadirat Allah SWT, kami mengundang Bapak/Ibu/Saudara/i untuk hadir pada acara syukuran khitanan putra kami:%0A%0A`;
    pesan += `*${namaAnak}*%0A`;
    pesan += `Putra dari ${ortu}%0A%0A`;
  }

  if(jenis=='maulid'){
    const tema = document.getElementById('temaMaulid').value;
    const penceramah = document.getElementById('penceramahMaulid').value;
    judul = 'UNDANGAN MAULID NABI';
    pesan = `*${judul} Muhammad SAW*%0A%0A`;
    pesan += `Mari hadir bersama dalam acara peringatan Maulid Nabi Muhammad SAW dengan tema:%0A`;
    pesan += `*${tema}*%0A%0A`;
    pesan += `Penceramah: ${penceramah}%0A%0A`;
  }

  if(jenis=='isra'){
    const tema = document.getElementById('temaIsra').value;
    const penceramah = document.getElementById('penceramahIsra').value;
    judul = "UNDANGAN ISRA' MI'RAJ";
    pesan = `*${judul}*%0A%0A`;
    pesan += `Dalam rangka memperingati Isra' Mi'raj Nabi Muhammad SAW dengan tema:%0A`;
    pesan += `*${tema}*%0A%0A`;
    pesan += `Penceramah: ${penceramah}%0A%0A`;
  }

  if(jenis=='haul'){
    const nama = document.getElementById('namaAlmarhum').value;
    const haulKe = document.getElementById('haulKe').value;
    judul = 'UNDANGAN HAUL/TAHLIL';
    pesan = `*${judul}*%0A%0A`;
    pesan += `Dengan memohon doa restu, kami mengundang Bapak/Ibu/Saudara/i untuk hadir pada acara haul ke-${haulKe} almarhum/almarhumah:%0A%0A`;
    pesan += `*${nama}*%0A%0A`;
  }

  pesan += `📅 ${tanggalFormat}%0A`;
  pesan += `🕐 ${jam} WITA%0A`;
  pesan += `📍 ${tempat}%0A%0A`;
  if(ucapan) pesan += `${ucapan}%0A%0A`;
  pesan += `Kehadiran Bapak/Ibu/Saudara/i merupakan suatu kehormatan bagi kami.%0A`;
  pesan += `Wassalamu'alaikum Wr. Wb.`;

  let waFormat = waTeman;
  if(waFormat.startsWith('0')) waFormat = '62' + waFormat.substring(1);

  window.open(`https://wa.me/${waFormat}?text=${pesan}`,'_blank');
  alert('Undangan terkirim ke WhatsApp teman!');
  closeModal();
}

let itemCounter = 5;
function renderNota(){
  const html = [];
  for(let i=1;i<=5;i++){
    html.push(`<div class="item-row"><input type="text" class="input" placeholder="Nama Barang" id="notaNama${i}"><input type="number" class="input" placeholder="Harga" id="notaHarga${i}" oninput="hitungTotalNota()"><input type="number" class="input" placeholder="Qty" id="notaQty${i}" value="1" oninput="hitungTotalNota()"></div>`);
  }
  document.getElementById('notaItems').innerHTML = html.join('');
  hitungTotalNota();
}

function tambahItemNota(){
  itemCounter++;
  const div = document.createElement('div');
  div.className='item-row';
  div.innerHTML=`<input type="text" class="input" placeholder="Nama Barang" id="notaNama${itemCounter}"><input type="number" class="input" placeholder="Harga" id="notaHarga${itemCounter}" oninput="hitungTotalNota()"><input type="number" class="input" placeholder="Qty" id="notaQty${itemCounter}" value="1" oninput="hitungTotalNota()"><button onclick="this.parentElement.remove();hitungTotalNota()" style="background:var(--danger);color:#fff;border:none;border-radius:6px;padding:0 10px;height:40px">x</button>`;
  document.getElementById('notaItems').appendChild(div);
}

function hitungTotalNota(){
  let total = 0;
  document.querySelectorAll('.item-row').forEach(row=>{
    const hargaEl = row.querySelector('input:nth-child(2)');
    const qtyEl = row.querySelector('input:nth-child(3)');
    const harga = parseInt(hargaEl.value) || 0;
    const qty = parseInt(qtyEl.value) || 0;
    total += harga * qty;
  });
  const ongkir = parseInt(document.getElementById('notaOngkir').value) || 0;
  document.getElementById('notaTotal').innerText = 'Rp'+(total+ongkir).toLocaleString('id-ID');
}

function kirimNotaWA(){
  const waPelanggan = document.getElementById('notaWA').value.replace(/[^0-9]/g,'');
  if(!waPelanggan || waPelanggan.length < 10){
    alert('Isi No WA Pelanggan dengan benar!');
    return;
  }

  let pesan = `*NOTA DIGITAL KURIR SUPRA*%0A%0A`;
  let total = 0;
  let no = 1;
  document.querySelectorAll('.item-row').forEach(row=>{
    const nama = row.querySelector('input:nth-child(1)').value;
    const harga = parseInt(row.querySelector('input:nth-child(2)').value) || 0;
    const qty = parseInt(row.querySelector('input:nth-child(3)').value) || 0;
    const jumlah = harga * qty;
    if(nama && harga && qty){
      total += jumlah;
      pesan += `${no}. ${nama}%0A`;
      pesan += ` Harga: Rp${harga.toLocaleString('id-ID')}%0A`;
      pesan += ` Qty: ${qty}%0A`;
      pesan += ` Jumlah: Rp${jumlah.toLocaleString('id-ID')}%0A%0A`;
      no++;
    }
  });
  const ongkir = parseInt(document.getElementById('notaOngkir').value) || 0;
  total += ongkir;
  pesan += `Ongkir: Rp${ongkir.toLocaleString('id-ID')}%0A`;
  pesan += `*TOTAL: Rp${total.toLocaleString('id-ID')}*`;

  let waFormat = waPelanggan;
  if(waFormat.startsWith('0')) waFormat = '62' + waFormat.substring(1);

  window.open(`https://wa.me/${waFormat}?text=${pesan}`,'_blank');
}

// BELANJAAN 10 KOLOM
function tambahBelanja(){
  const i = document.querySelectorAll('#belanjaList input').length + 1;
  if(i>10){alert('Max 10 item');return}
  const input = document.createElement('input');
  input.type='text';
  input.className='input';
  input.id='belanja'+i;
  input.placeholder=`Item ${i}`;
  input.style.marginBottom='8px';
  document.getElementById('belanjaList').appendChild(input);
}

// AKUN AUTO SAVE
function loadAkun(){
  document.getElementById('akunNama').value = akun.nama;
  document.getElementById('akunAlamat').value = akun.alamat;
  document.getElementById('akunWA').value = akun.wa;
}
function saveAkun(){
  akun = {
    nama:document.getElementById('akunNama').value,
    alamat:document.getElementById('akunAlamat').value,
    wa:document.getElementById('akunWA').value
  };
  localStorage.setItem('kurir_akun',JSON.stringify(akun));
}

// RIWAYAT
function renderRiwayat(){
  if(riwayat.length==0){
    document.getElementById('riwayatList').innerHTML='<p style="text-align:center;color:var(--gray-500)">Belum ada riwayat</p>';
    return;
  }
  const html = riwayat.map(r=>`
    <div class="card">
      <div style="display:flex;justify-content:space-between;margin-bottom:8px">
        <span class="badge">${r.jenis}</span>
        <button onclick="hapusRiwayat(${r.id})" style="background:var(--danger);color:#fff;border:none;border-radius:6px;padding:4px 8px;font-size:12px">Hapus</button>
      </div>
      <div style="font-size:13px;color:var(--gray-700)">${r.detail}</div>
      <div style="font-size:11px;color:var(--gray-500);margin-top:8px">${r.tanggal}</div>
    </div>
  `).join('');
  document.getElementById('riwayatList').innerHTML=html;
}
function hapusRiwayat(id){
  if(confirm('Hapus riwayat ini?')){
    riwayat = riwayat.filter(r=>r.id!=id);
    localStorage.setItem('kurir_riwayat',JSON.stringify(riwayat));
    renderRiwayat();
  }
}

// Close modal klik luar
document.querySelectorAll('.modal').forEach(m=>{
  m.addEventListener('click',e=>{
    if(e.target==m) closeModal();
  });
});

// Init belanja 10 kolom
for(let i=1;i<=10;i++){
  const input = document.createElement('input');
  input.type='text';
  input.className='input';
  input.id='belanja'+i;
  input.placeholder=`Item ${i}`;
  input.style.marginBottom='8px';
  document.getElementById('belanjaList').appendChild(input);
}
</script>
</body>
</html>
