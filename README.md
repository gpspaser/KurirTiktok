<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kurir TikTok - Paman Kurir Siap Melayani</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
<link rel='stylesheet' href='https://cdn-uicons.flaticon.com/2.6.0/uicons-solid-rounded/css/uicons-solid-rounded.css'>
<link rel='stylesheet' href='https://cdn-uicons.flaticon.com/2.6.0/uicons-brands/css/uicons-brands.css'>
<style>
:root{--neon-orange:#FF6B00;--neon-blue:#00D4FF;--neon-pink:#FF00FF;--neon-green:#00FF88;--bg:#0a0a1a;--card:#1a1a2e;--putih:#fff;--gray:#aaa;--wa:#25D366}
*{margin:0;padding:0;box-sizing:border-box;font-family:'Poppins',sans-serif}
body{background:var(--bg);color:var(--putih);min-height:100vh;background-image:radial-gradient(circle at 20% 50%,rgba(0,212,255,0.1) 0%,transparent 50%),radial-gradient(circle at 80% 20%,rgba(255,0,255,0.1) 0%,transparent 50%)}

.header{text-align:center;padding:24px 16px;background:linear-gradient(135deg,rgba(255,107,0,0.2),rgba(0,212,255,0.2));border-bottom:2px solid var(--neon-orange);box-shadow:0 0 30px rgba(255,107,0,0.3)}
.header h1{font-size:28px;font-weight:700;background:linear-gradient(90deg,#FF6B00,#00D4FF);-webkit-background-clip:text;-webkit-text-fill-color:transparent;text-shadow:0 0 20px rgba(0,212,255,0.5)}
.header p{font-size:12px;color:var(--neon-blue);margin-top:6px;font-weight:600}

.jam-box{background:rgba(0,212,255,0.1);border:1px solid var(--neon-blue);border-radius:12px;padding:14px;margin:16px;text-align:center;box-shadow:0 0 15px rgba(0,212,255,0.2)}
.jam-title{font-size:11px;color:var(--neon-blue);font-weight:700;margin-bottom:8px}
.jam-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;font-size:12px}
.jam-item{background:rgba(0,0,0,0.4);padding:8px;border-radius:8px;border:1px solid rgba(255,107,0,0.3)}
.jam-item b{color:var(--neon-orange)}

.container{padding:16px;padding-bottom:80px}
.grid-layanan{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.layanan-card{
  background:var(--card);
  border-radius:16px;
  padding:18px 12px;
  text-align:center;
  cursor:pointer;
  border:2px solid transparent;
  transition:0.3s;
  position:relative;
  overflow:hidden;
}
.layanan-card::before{
  content:'';
  position:absolute;
  top:-2px;left:-2px;right:-2px;bottom:-2px;
  background:linear-gradient(45deg,var(--neon-orange),var(--neon-blue),var(--neon-pink));
  border-radius:16px;
  z-index:-1;
  opacity:0;
  transition:0.3s;
}
.layanan-card:hover::before{opacity:1}
.layanan-card:active{transform:scale(0.95)}
.layanan-icon{font-size:40px;margin-bottom:10px;display:block;filter:drop-shadow(0 0 10px currentColor)}
.layanan-card:nth-child(1){color:var(--neon-blue)}
.layanan-card:nth-child(2){color:var(--neon-green)}
.layanan-card:nth-child(3){color:var(--neon-orange)}
.layanan-card:nth-child(4){color:var(--neon-pink)}
.layanan-nama{font-size:14px;font-weight:700;margin-bottom:4px}
.layanan-desc{font-size:10px;color:var(--gray);line-height:1.3}

.wa-float{position:fixed;bottom:20px;right:16px;background:var(--wa);color:var(--putih);border:none;border-radius:50px;padding:14px 20px;font-weight:700;font-size:13px;box-shadow:0 4px 20px rgba(37,211,102,0.5);cursor:pointer;display:flex;align-items:center;gap:8px;z-index:999}

/* MODAL */
.modal{display:none;position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.8);backdrop-filter:blur(5px);z-index:2000;align-items:center;justify-content:center}
.modal.active{display:flex}
.modal-content{
  background:var(--card);
  width:92%;
  max-width:420px;
  border-radius:20px;
  padding:20px;
  border:2px solid var(--neon-blue);
  box-shadow:0 0 40px rgba(0,212,255,0.4);
  max-height:85vh;
  overflow-y:auto;
}
.modal-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:16px}
.modal-header h3{font-size:16px;font-weight:700;background:linear-gradient(90deg,var(--neon-orange),var(--neon-blue));-webkit-background-clip:text;-webkit-text-fill-color:transparent}
.close-btn{background:none;border:none;font-size:26px;cursor:pointer;color:var(--gray)}

.form-group{margin-bottom:12px}
.form-group label{display:block;font-size:12px;color:var(--neon-blue);margin-bottom:4px;font-weight:600}
.form-group label span{color:var(--neon-orange)}
.form-group input,.form-group textarea,select{
  width:100%;
  padding:10px;
  border:1px solid rgba(0,212,255,0.3);
  border-radius:8px;
  font-size:13px;
  background:rgba(0,0,0,0.4);
  color:var(--putih);
  font-family:'Poppins',sans-serif;
}
.form-group input:focus,.form-group textarea:focus{outline:none;border-color:var(--neon-orange);box-shadow:0 0 10px rgba(255,107,0,0.3)}
.form-group textarea{resize:vertical;min-height:60px}
.form-group input.error{border-color:var(--neon-orange)}
.error-text{color:var(--neon-orange);font-size:10px;margin-top:3px;display:none}

.btn-submit{
  width:100%;
  padding:14px;
  background:linear-gradient(135deg,var(--wa),#1EBE5D);
  color:var(--putih);
  border:none;
  border-radius:10px;
  font-weight:700;
  font-size:14px;
  cursor:pointer;
  display:flex;
  align-items:center;
  justify-content:center;
  gap:8px;
  margin-top:8px;
  box-shadow:0 4px 15px rgba(37,211,102,0.4);
}
.btn-submit:active{transform:scale(0.98)}

.save-info{font-size:10px;color:var(--neon-green);text-align:center;margin-top:8px;display:flex;align-items:center;justify-content:center;gap:4px}
</style>
</head>
<body>

<div class="header">
  <h1>Kurir TikTok</h1>
  <p>PAMAN KURIR SIAP MELAYANI!</p>
</div>

<div class="jam-box">
  <div class="jam-title">JADWAL OPERASIONAL</div>
  <div class="jam-grid">
    <div class="jam-item"><b>Senin-Kamis & Sabtu</b><br>08:00 - 17:00</div>
    <div class="jam-item"><b>Jum'at Pagi</b><br>08:00 - 11:00</div>
    <div class="jam-item" style="grid-column:span 2"><b>Jum'at Siang</b><br>14:00 - 17:00</div>
  </div>
</div>

<div class="container">
  <div class="grid-layanan">
    <div class="layanan-card" onclick="openModal('ojek')">
      <i class="fi fi-sr-motorcycle layanan-icon"></i>
      <div class="layanan-nama">OJEK</div>
      <div class="layanan-desc">Antar Jemput Penumpang Cepat!</div>
    </div>
    <div class="layanan-card" onclick="openModal('food')">
      <i class="fi fi-sr-shopping-bag layanan-icon"></i>
      <div class="layanan-nama">FOOD & SHOPS</div>
      <div class="layanan-desc">Beli Makanan & Belanjaan Mudah!</div>
    </div>
    <div class="layanan-card" onclick="openModal('delivery')">
      <i class="fi fi-sr-box layanan-icon"></i>
      <div class="layanan-nama">DELIVERY</div>
      <div class="layanan-desc">Kirim Paket Aman & Cepat!</div>
    </div>
    <div class="layanan-card" onclick="openModal('ambil')">
      <i class="fi-sr-shopping-bag layanan-icon"></i>
      <div class="layanan-nama">AMBIL PESAN</div>
      <div class="layanan-desc">Ambil Barang atau Pesanan Anda!</div>
    </div>
  </div>
</div>

<a href="https://wa.me/6283137527300" target="_blank" class="wa-float">
  <i class="fi fi-brands-whatsapp"></i> 083137527300
</a>

<!-- MODAL OJEK -->
<div class="modal" id="modalOjek">
  <div class="modal-content">
    <div class="modal-header">
      <h3><i class="fi fi-sr-motorcycle"></i> Form Ojek</h3>
      <button class="close-btn" onclick="closeModal('ojek')">&times;</button>
    </div>
    <div class="form-group">
      <label>Nama Penumpang <span>*</span></label>
      <input type="text" id="ojekNama" placeholder="Nama lengkap">
      <div class="error-text" id="errOjekNama">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>No WhatsApp <span>*</span></label>
      <input type="tel" id="ojekWA" placeholder="08xxxxxxxxxx" oninput="autoSave()">
      <div class="error-text" id="errOjekWA">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Alamat Jemput <span>*</span></label>
      <textarea id="ojekJemput" placeholder="Titik jemput lengkap"></textarea>
      <div class="error-text" id="errOjekJemput">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Tujuan <span>*</span></label>
      <textarea id="ojekTujuan" placeholder="Alamat tujuan"></textarea>
      <div class="error-text" id="errOjekTujuan">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Catatan</label>
      <textarea id="ojekCatatan" placeholder="Catatan tambahan"></textarea>
    </div>
    <div class="save-info"><i class="fi fi-sr-disk"></i>Data auto save otomatis</div>
    <button class="btn-submit" onclick="submitOjek()"><i class="fi fi-brands-whatsapp"></i> Order via WhatsApp</button>
  </div>
</div>

<!-- MODAL FOOD & SHOPS -->
<div class="modal" id="modalFood">
  <div class="modal-content">
    <div class="modal-header">
      <h3><i class="fi fi-sr-shopping-bag"></i> Form Food & Shops</h3>
      <button class="close-btn" onclick="closeModal('food')">&times;</button>
    </div>
    <div class="form-group">
      <label>Nama Pemesan <span>*</span></label>
      <input type="text" id="foodNama" placeholder="Nama lengkap">
      <div class="error-text" id="errFoodNama">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>No WhatsApp <span>*</span></label>
      <input type="tel" id="foodWA" placeholder="08xxxxxxxxxx" oninput="autoSave()">
      <div class="error-text" id="errFoodWA">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Beli di Toko/Resto <span>*</span></label>
      <input type="text" id="foodToko" placeholder="Nama toko/resto">
      <div class="error-text" id="errFoodToko">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Detail Pesanan <span>*</span></label>
      <textarea id="foodDetail" placeholder="Sebutkan menu/barang yang dibeli + qty"></textarea>
      <div class="error-text" id="errFoodDetail">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Alamat Antar <span>*</span></label>
      <textarea id="foodAlamat" placeholder="Alamat lengkap pengantaran" oninput="autoSave()"></textarea>
      <div class="error-text" id="errFoodAlamat">Wajib diisi</div>
    </div>
    <div class="save-info"><i class="fi fi-sr-disk"></i>Data auto save otomatis</div>
    <button class="btn-submit" onclick="submitFood()"><i class="fi fi-brands-whatsapp"></i> Order via WhatsApp</button>
  </div>
</div>

<!-- MODAL DELIVERY -->
<div class="modal" id="modalDelivery">
  <div class="modal-content">
    <div class="modal-header">
      <h3><i class="fi fi-sr-box"></i> Form Delivery Paket</h3>
      <button class="close-btn" onclick="closeModal('delivery')">&times;</button>
    </div>
    <div class="form-group">
      <label>Nama Pengirim <span>*</span></label>
      <input type="text" id="delNama" placeholder="Nama lengkap">
      <div class="error-text" id="errDelNama">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>No WhatsApp <span>*</span></label>
      <input type="tel" id="delWA" placeholder="08xxxxxxxxxx" oninput="autoSave()">
      <div class="error-text" id="errDelWA">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Alamat Penjemputan <span>*</span></label>
      <textarea id="delJemput" placeholder="Alamat ambil paket" oninput="autoSave()"></textarea>
      <div class="error-text" id="errDelJemput">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Alamat Tujuan <span>*</span></label>
      <textarea id="delTujuan" placeholder="Alamat kirim paket"></textarea>
      <div class="error-text" id="errDelTujuan">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Detail Paket <span>*</span></label>
      <textarea id="delDetail" placeholder="Isi paket, berat, ukuran"></textarea>
      <div class="error-text" id="errDelDetail">Wajib diisi</div>
    </div>
    <div class="save-info"><i class="fi fi-sr-disk"></i>Data auto save otomatis</div>
    <button class="btn-submit" onclick="submitDelivery()"><i class="fi fi-brands-whatsapp"></i> Order via WhatsApp</button>
  </div>
</div>

<!-- MODAL AMBIL PESAN -->
<div class="modal" id="modalAmbil">
  <div class="modal-content">
    <div class="modal-header">
      <h3><i class="fi fi-sr-store"></i> Form Ambil Pesanan</h3>
      <button class="close-btn" onclick="closeModal('ambil')">&times;</button>
    </div>
    <div class="form-group">
      <label>Nama Pemesan <span>*</span></label>
      <input type="text" id="ambilNama" placeholder="Nama lengkap">
      <div class="error-text" id="errAmbilNama">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>No WhatsApp <span>*</span></label>
      <input type="tel" id="ambilWA" placeholder="08xxxxxxxxxx" oninput="autoSave()">
      <div class="error-text" id="errAmbilWA">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Ambil di Toko <span>*</span></label>
      <input type="text" id="ambilToko" placeholder="Nama toko/resto">
      <div class="error-text" id="errAmbilToko">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Detail Pesanan <span>*</span></label>
      <textarea id="ambilDetail" placeholder="Kode order / nama pesanan"></textarea>
      <div class="error-text" id="errAmbilDetail">Wajib diisi</div>
    </div>
    <div class="form-group">
      <label>Alamat Pengantaran <span>*</span></label>
      <textarea id="ambilAlamat" placeholder="Alamat lengkap" oninput="autoSave()"></textarea>
      <div class="error-text" id="errAmbilAlamat">Wajib diisi</div>
    </div>
    <div class="save-info"><i class="fi fi-sr-disk"></i>Data auto save otomatis</div>
    <button class="btn-submit" onclick="submitAmbil()"><i class="fi fi-brands-whatsapp"></i> Order via WhatsApp</button>
  </div>
</div>

<script>
const NO_WA = "083137527300";

init();
function init(){
  loadDataPelanggan();
}

// AUTO SAVE DATA PELANGGAN
function autoSave(){
  const data = {
    nama: document.getElementById('ojekNama').value || document.getElementById('foodNama').value || document.getElementById('delNama').value || document.getElementById('ambilNama').value,
    wa: document.getElementById('ojekWA').value || document.getElementById('foodWA').value || document.getElementById('delWA').value || document.getElementById('ambilWA').value,
    alamat: document.getElementById('foodAlamat').value || document.getElementById('delJemput').value || document.getElementById('ambilAlamat').value
  };
  localStorage.setItem('kurir_tiktok_pelanggan', JSON.stringify(data));
}

function loadDataPelanggan(){
  const data = localStorage.getItem('kurir_tiktok_pelanggan');
  if(data){
    const d = JSON.parse(data);
    ['ojekNama','foodNama','delNama','ambilNama'].forEach(id=>{
      if(document.getElementById(id)) document.getElementById(id).value = d.nama || '';
    });
    ['ojekWA','foodWA','delWA','ambilWA'].forEach(id=>{
      if(document.getElementById(id)) document.getElementById(id).value = d.wa || '';
    });
    ['foodAlamat','delJemput','ambilAlamat'].forEach(id=>{
      if(document.getElementById(id)) document.getElementById(id).value = d.alamat || '';
    });
  }
}

function openModal(type){
  document.getElementById('modal'+type.charAt(0).toUpperCase()+type.slice(1)).classList.add('active');
  loadDataPelanggan();
}

function closeModal(type){
  document.getElementById('modal'+type.charAt(0).toUpperCase()+type.slice(1)).classList.remove('active');
}

function validasi(ids){
  let valid = true;
  ids.forEach(id=>{
    const el = document.getElementById(id);
    const err = document.getElementById('err'+id.charAt(0).toUpperCase()+id.slice(1));
    el.classList.remove('error');
    err.style.display = 'none';
    if(!el.value.trim()){
      el.classList.add('error');
      err.style.display = 'block';
      valid = false;
    }
  });
  return valid;
}

function submitOjek(){
  if(!validasi(['ojekNama','ojekWA','ojekJemput','ojekTujuan'])) return;
  autoSave();
  let pesan = `*ORDER OJEK - KURIR TIKTOK* 🏍️\n\n`;
  pesan += `Nama: ${document.getElementById('ojekNama').value}\n`;
  pesan += `WA: ${document.getElementById('ojekWA').value}\n`;
  pesan += `Jemput: ${document.getElementById('ojekJemput').value}\n`;
  pesan += `Tujuan: ${document.getElementById('ojekTujuan').value}\n`;
  if(document.getElementById('ojekCatatan').value) pesan += `Catatan: ${document.getElementById('ojekCatatan').value}`;
  window.open(`https://wa.me/62${NO_WA.substring(1)}?text=${encodeURIComponent(pesan)}`,'_blank');
  closeModal('ojek');
}

function submitFood(){
  if(!validasi(['foodNama','foodWA','foodToko','foodDetail','foodAlamat'])) return;
  autoSave();
  let pesan = `*ORDER FOOD & SHOPS - KURIR TIKTOK* 🛍️\n\n`;
  pesan += `Nama: ${document.getElementById('foodNama').value}\n`;
  pesan += `WA: ${document.getElementById('foodWA').value}\n`;
  pesan += `Beli di: ${document.getElementById('foodToko').value}\n`;
  pesan += `Pesanan: ${document.getElementById('foodDetail').value}\n`;
  pesan += `Alamat Antar: ${document.getElementById('foodAlamat').value}`;
  window.open(`https://wa.me/62${NO_WA.substring(1)}?text=${encodeURIComponent(pesan)}`,'_blank');
  closeModal('food');
}

function submitDelivery(){
  if(!validasi(['delNama','delWA','delJemput','delTujuan','delDetail'])) return;
  autoSave();
  let pesan = `*ORDER DELIVERY PAKET - KURIR TIKTOK* 📦\n\n`;
  pesan += `Nama: ${document.getElementById('delNama').value}\n`;
  pesan += `WA: ${document.getElementById('delWA').value}\n`;
  pesan += `Jemput: ${document.getElementById('delJemput').value}\n`;
  pesan += `Tujuan: ${document.getElementById('delTujuan').value}\n`;
  pesan += `Detail: ${document.getElementById('delDetail').value}`;
  window.open(`https://wa.me/62${NO_WA.substring(1)}?text=${encodeURIComponent(pesan)}`,'_blank');
  closeModal('delivery');
}

function submitAmbil(){
  if(!validasi(['ambilNama','ambilWA','ambilToko','ambilDetail','ambilAlamat'])) return;
  autoSave();
  let pesan = `*ORDER AMBIL PESAN - KURIR TIKTOK* 🏪\n\n`;
  pesan += `Nama: ${document.getElementById('ambilNama').value}\n`;
  pesan += `WA: ${document.getElementById('ambilWA').value}\n`;
  pesan += `Ambil di: ${document.getElementById('ambilToko').value}\n`;
  pesan += `Pesanan: ${document.getElementById('ambilDetail').value}\n`;
  pesan += `Alamat Antar: ${document.getElementById('ambilAlamat').value}`;
  window.open(`https://wa.me/62${NO_WA.substring(1)}?text=${encodeURIComponent(pesan)}`,'_blank');
  closeModal('ambil');
}
</script>
</body>
</html>
