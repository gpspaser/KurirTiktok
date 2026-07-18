<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GPS KURIR-Tanahgrogot</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
<link rel='stylesheet' href='https://cdn-uicons.flaticon.com/2.6.0/uicons-brands/css/uicons-brands.css'>
<link rel='stylesheet' href='https://cdn-uicons.flaticon.com/2.6.0/uicons-solid-rounded/css/uicons-solid-rounded.css'>
<style>
:root{--gold:#FFD700;--hitam:#0d0d0d;--hitam2:#1a1a1a;--putih:#fff;--abu:#ccc;--hijau:#25D366}
*{margin:0;padding:0;box-sizing:border-box;font-family:'Poppins',sans-serif}
body{background:var(--hitam);color:var(--putih);padding-bottom:70px}
.header{position:fixed;top:0;left:0;right:0;background:var(--hitam2);color:var(--gold);padding:12px 16px;z-index:1000;display:flex;justify-content:space-between;align-items:center;border-bottom:2px solid var(--gold)}
.header h1{font-size:16px;font-weight:700}
.header-date{text-align:right;font-size:11px;color:var(--abu)}
.marquee{background:var(--gold);color:var(--hitam);padding:6px;overflow:hidden;white-space:nowrap;margin-top:52px;font-weight:600;font-size:12px}
.marquee span{display:inline-block;animation:marq 30s linear infinite}
@keyframes marq{0%{transform:translateX(100%)}100%{transform:translateX(-100%)}}
.container{padding:16px}
.section-title{font-size:14px;font-weight:700;margin:14px 0 8px;color:var(--gold);border-left:3px solid var(--gold);padding-left:8px}
.layanan-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.layanan-card{background:var(--hitam2);border:1px solid #333;border-radius:12px;padding:20px 14px;text-align:center;cursor:pointer;transition:0.2s}
.layanan-card:hover{border-color:var(--gold);transform:translateY(-3px)}
.layanan-card i{font-size:32px;color:var(--gold);margin-bottom:8px;display:block}
.layanan-card span{font-size:13px;font-weight:700}
.tarif-info-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:8px}
.tarif-info-card{background:var(--hitam2);border:1px dashed #555;border-radius:8px;padding:8px;text-align:center;font-size:11px;color:var(--abu)}
.tarif-info-km{font-weight:700;color:var(--gold)}
.tarif-info-note{font-size:10px;color:var(--abu);margin-top:10px;text-align:center;font-style:italic}
.modal{display:none;position:fixed;top:0;left:0;right:0;bottom:0;background:rgba(0,0,0,0.9);z-index:2000;align-items:center;justify-content:center;padding:16px}
.modal.active{display:flex}
.modal-content{background:var(--hitam2);width:100%;max-width:420px;border-radius:16px;padding:16px;border:1px solid var(--gold);max-height:90vh;overflow-y:auto}
.modal-header{display:flex;justify-content:space-between;align-items:center;border-bottom:1px solid #333;padding-bottom:10px;margin-bottom:12px}
.modal-header h3{font-size:16px;color:var(--gold)}
.close-btn{background:none;border:none;font-size:24px;color:var(--abu);cursor:pointer}
.form-group{margin-bottom:10px}
.form-group label{display:block;font-size:11px;font-weight:600;margin-bottom:3px;color:var(--putih)}
.form-group label span{color:red}
.form-group input,.form-group textarea{width:100%;padding:10px;border:1px solid #444;border-radius:6px;font-size:12px;background:#222;color:var(--putih)}
.btn-wa{width:100%;padding:12px;background:var(--hijau);color:var(--putih);border:none;border-radius:8px;font-weight:700;font-size:14px;cursor:pointer;display:flex;align-items:center;justify-content:center;gap:6px;margin-top:12px}
.bottom-nav{position:fixed;bottom:0;left:0;right:0;background:var(--hitam2);display:flex;justify-content:space-around;padding:8px 0;border-top:2px solid var(--gold);z-index:1000}
.nav-item{display:flex;flex-direction:column;align-items:center;gap:3px;color:var(--abu);font-size:10px;cursor:pointer}
.nav-item.active{color:var(--gold)}
.nav-item i{font-size:20px}
.page{display:none}
.page.active{display:block}
.notif{position:fixed;top:60px;left:50%;transform:translateX(-50%);background:var(--gold);color:var(--hitam);padding:8px 16px;border-radius:20px;font-size:12px;font-weight:700;z-index:3000;display:none}
.notif.active{display:block}
</style>
</head>
<body>

<div class="notif" id="notif">Data tersimpan otomatis ✅</div>
<div class="header">
  <h1>GPS PASER   ===🛵</h1>
  
  <div class="header-date"><div id="hari">Minggu</div><div id="tanggal">27 Sep 2026</div></div>
</div>
<div class="marquee"><span>🔥 Info Admin hub: 0831-3752-7300 || Operasional jam 08:00-17:00 WITA || Istirahat : Waktu Sholat || Tarif sewaktu-waktu dapat berubah ||💸Pembayaran COD-Tranfer Dana & ShopeePay🔥</span></div>

<div class="page active" id="pageHome">
  <div class="container">
    <div class="section-title">Pilih Layanan </div>
    <div class="layanan-grid">
      <div class="layanan-card" onclick="openModal('BELIKAN')"><i class="fi fi-sr-shopping-bag"></i><span>BELIKAN</span></div>
      <div class="layanan-card" onclick="openModal('ANTARKAN')"><i class="fi fi-sr-truck-side"></i><span>ANTARKAN</span></div>
      <div class="layanan-card" onclick="openModal('AMBILKAN')"><i class="fi fi-sr-box-open"></i><span>AMBILKAN</span></div>
      <div class="layanan-card" onclick="openModal('OJEK')"><i class="fi fi-sr-motorcycle"></i><span>OJEK</span></div>
    </div>

    <div class="section-title" style="margin-top:20px;"> Tarif Ongkir</div>
    <div class="tarif-info-grid">
      <div class="tarif-info-card"><div class="tarif-info-km">0-2km</div><div>Rp10.000</div></div>
      <div class="tarif-info-card"><div class="tarif-info-km">3km</div><div>Rp15.000</div></div>
      <div class="tarif-info-card"><div class="tarif-info-km">4km</div><div>Rp20.000</div></div>
      <div class="tarif-info-card"><div class="tarif-info-km">5km</div><div>Rp25.000</div></div>
      <div class="tarif-info-card"><div class="tarif-info-km">6km</div><div>Rp30.000</div></div>
      <div class="tarif-info-card"><div class="tarif-info-km">7km</div><div>Rp.35.000</div></div>
    </div>
    <div class="tarif-info-note">* Maximal barang bawaan 15kg,tambah tempat harga up & kesepakatan dengan admin</div>
  </div>
</div>

<div class="page" id="pageAkun">
  <div class="container">
    <div class="section-title">Data Akun Tersimpan</div>
    <div class="form-group"><label>Nama</label><input type="text" id="akunNama" oninput="saveData()"></div>
    <div class="form-group"><label>WA</label><input type="tel" id="akunWA" oninput="saveData()"></div>
    <div class="form-group"><label>Alamat</label><textarea id="akunAlamat" rows="3" oninput="saveData()"></textarea></div>
  </div>
</div>

<div class="modal" id="modalForm">
  <div class="modal-content">
    <div class="modal-header">
      <h3 id="modalTitle">Order Layanan</h3>
      <button class="close-btn" onclick="closeModal()">&times;</button>
    </div>
    
    <div class="form-group"><label>Nama Lengkap <span>*</span></label><input type="text" id="coNama" oninput="saveData()"></div>
    <div class="form-group"><label>No.WA <span>*</span></label><input type="tel" id="coWA" oninput="saveData()"></div>
    <div class="form-group"><label>Alamat <span>*</span></label><textarea id="coAlamat" rows="2" oninput="saveData()"></textarea></div>
    <div id="formDinamis"></div>
    <button class="btn-wa" onclick="kirimWA()"><i class="fi fi-brands-whatsapp"></i> Kirim ke Admin</button>
  </div>
</div>

<div class="bottom-nav">
  <div class="nav-item active" onclick="switchPage('Home')"><i class="fi fi-sr-home"></i><span>Home</span></div>
  <div class="nav-item" onclick="switchPage('Akun')"><i class="fi fi-sr-user"></i><span>Akun</span></div>
</div>

<script>
const NO_WA_ADMIN = "083137527300";
let layananAktif = '';
let saveTimer;

init();
function init(){ updateTanggal(); loadData(); }

function updateTanggal(){
  const now = new Date();
  document.getElementById('hari').innerText = new Intl.DateTimeFormat("id-ID", {weekday:"long",timeZone:"Asia/Makassar"}).format(now);
  document.getElementById('tanggal').innerText = new Intl.DateTimeFormat("id-ID", {day:"2-digit",month:"2-digit",year:"numeric",timeZone:"Asia/Makassar"}).format(now);
}

// AUTO SAVE KE BROWSER
function saveData(){
  clearTimeout(saveTimer);
  saveTimer = setTimeout(()=>{
    const data = {nama:document.getElementById('coNama').value,wa:document.getElementById('coWA').value,alamat:document.getElementById('coAlamat').value};
    localStorage.setItem('kurirpaser',JSON.stringify(data));
    ['akunNama','akunWA','akunAlamat'].forEach(id=>{document.getElementById(id).value=data[id.replace('akun','').toLowerCase()];});
    document.getElementById('notif').classList.add('active');
    setTimeout(()=>document.getElementById('notif').classList.remove('active'),1500);
  },800);
}
// AUTO LOAD DARI BROWSER
function loadData(){
  const d = JSON.parse(localStorage.getItem('kurirpaser')||'{}');
  ['coNama','coWA','coAlamat','akunNama','akunWA','akunAlamat'].forEach(id=>{
    document.getElementById(id).value = d[id.replace('co','').replace('akun','') ]||'';
  });
}

function openModal(jenis){
  layananAktif = jenis;
  document.getElementById('modalTitle').innerText = `Order ${jenis}`;
  let html = '';
  if(jenis=='BELIKAN'){ html = `<div class="form-group"><label>Beli di: Toko & Alamat</label><input type="text" id="beliDi"></div><div class="form-group"><label>Keterangan Barang</label><textarea id="beliKet" rows="2"></textarea></div>`; }
  if(jenis=='ANTARKAN'){ html = `<div class="form-group"><label>Alamat Antar</label><input type="text" id="antarAlamat"></div><div class="form-group"><label>Nama Penerima</label><input type="text" id="antarNama"></div><div class="form-group"><label>No.WA Penerima</label><input type="tel" id="antarWA"></div>`; }
  if(jenis=='AMBILKAN'){ html = `<div class="form-group"><label>Ambil di: Alamat</label><input type="text" id="ambilDi"></div><div class="form-group"><label>Keterangan</label><textarea id="ambilKet" rows="2"></textarea></div><div class="form-group"><label>Note: WA Toko</label><input type="tel" id="ambilWA"></div>`; }
  if(jenis=='OJEK'){ html = `<div class="form-group"><label>Jemput di:</label><input type="text" id="ojekJemput"></div><div class="form-group"><label>Tujuan Ke:</label><input type="text" id="ojekTujuan"></div><div class="form-group"><label>Note: </label><input type="text" id="ojekHub"></div>`; }
  document.getElementById('formDinamis').innerHTML = html;
  document.getElementById('modalForm').classList.add('active');
  document.body.style.overflow='hidden';
}
function closeModal(){ document.getElementById('modalForm').classList.remove('active'); document.body.style.overflow='auto'; }

function kirimWA(){
  const nama = document.getElementById('coNama').value.trim();
  const wa = document.getElementById('coWA').value.trim();
  const alamat = document.getElementById('coAlamat').value.trim();
  
  if(!nama || !wa || !alamat){
    alert('Isi Nama, WA, Alamat wajib');
    return;
  }
  
  const tgl = new Intl.DateTimeFormat("id-ID", {day:"2-digit",month:"2-digit",year:"numeric",timeZone:"Asia/Makassar"}).format(new Date());
  const hari = new Intl.DateTimeFormat("id-ID", {weekday:"long",timeZone:"Asia/Makassar"}).format(new Date());
  
  // Menggunakan emoji standar WhatsApp agar dipastikan terbaca di semua device
  let pesan = `*ORDER BARU ${hari.toUpperCase()}, ${tgl}*\n\n` +
              `👤 *DATA PELANGGAN:*\n` +
              `==================\n` +
              `Nama : ${nama}\n` +
              `No.wa : ${wa}\n` +
              `Alamat : ${alamat}\n\n` +
              `🛵 *LAYANAN : ${layananAktif}*\n` +
              `==================\n`;
  
  if(layananAktif=='BELIKAN'){ 
    pesan += `📍 Beli di: ${document.getElementById('beliDi').value || '-'}\n▪️ Keterangan: ${document.getElementById('beliKet').value || '-'}\n`; 
  }
  if(layananAktif=='ANTARKAN'){ 
    pesan += `📍 Alamat antar: ${document.getElementById('antarAlamat').value || '-'}\n▪️ Nama Penerima: ${document.getElementById('antarNama').value || '-'}\n▪️ No.wa: ${document.getElementById('antarWA').value || '-'}\n`; 
  }
  if(layananAktif=='AMBILKAN'){ 
    pesan += `📍 Ambil di: ${document.getElementById('ambilDi').value || '-'}\n▪️ Keterangan: ${document.getElementById('ambilKet').value || '-'}\n▪️ Note: wa tokonya: ${document.getElementById('ambilWA').value || '-'}\n`; 
  }
  if(layananAktif=='OJEK'){ 
    pesan += `📍 Jemput di: ${document.getElementById('ojekJemput').value || '-'}\n▪️ Tujuan Ke: ${document.getElementById('ojekTujuan').value || '-'}\n▪️ Note: ${document.getElementById('ojekHub').value || '-'}\n`; 
  }
  
  pesan += `\nMohon segera diproses ya kak 🙏`;
  
  // Memastikan format nomor HP Admin benar (menghilangkan angka 0 di depan dan diganti 62)
  const formattedAdminWA = NO_WA_ADMIN.startsWith('0') ? '62' + NO_WA_ADMIN.substring(1) : NO_WA_ADMIN;
  
  // Buka link WhatsApp dengan pesan yang sudah di-encode sempurna
  const urlUrl = `https://api.whatsapp.com/send?phone=${formattedAdminWA}&text=${encodeURIComponent(pesan)}`;
  
  window.open(urlUrl, '_blank');
  closeModal();
}
function switchPage(p){ document.querySelectorAll('.page').forEach(x=>x.classList.remove('active')); document.querySelectorAll('.nav-item').forEach(x=>x.classList.remove('active')); document.getElementById('page'+p).classList.add('active'); event.target.closest('.nav-item').classList.add('active'); }
</script>
</body>
</html>
