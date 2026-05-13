<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<meta name="theme-color" content="#FE2C55">
<title>🚀</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif}
body{background:#F5F5F5;color:#212121;font-size:14px;padding-bottom:70px;padding-top:88px}
.header-wrap{position:fixed;top:0;left:0;right:0;z-index:99;background:#fff}
.header{background:#fff;padding:15px 15px 10px;border-bottom:1px solid #eee;display:flex;justify-content:space-between;align-items:center}
.logo{font-size:24px;font-weight:800}
.logo .hitam{color:#000}
.logo .merah{color:#FE2C55}
.kota{font-size:14px;color:#757575;font-weight:600}
.status-bar{background:#4CAF50;color:#fff;text-align:center;padding:6px;font-size:12px;font-weight:600}
.status-bar.offline{background:#F44336}
.card{background:#fff;margin:10px 15px;border-radius:12px;padding:15px}
.card input,.card textarea{width:100%;padding:12px;border:1px solid #E0E0E0;border-radius:8px;font-size:15px;margin-top:5px}
.card input:focus,.card textarea:focus{outline:none;border-color:#FE2C55}
.label{font-size:12px;color:#757575;margin-top:10px}
.info-bar{display:flex;margin:10px 15px;border-radius:12px;overflow:hidden;background:#fff}
.info-bar > div{flex:1;padding:14px;text-align:center;font-weight:600}
.info-bar i{margin-right:6px}
.jam{color:#FE2C55}
.grid{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin:15px}
.layanan{background:#fff;border-radius:12px;padding:12px 5px;text-align:center;border:2px solid transparent;transition:.2s;cursor:pointer}
.layanan.active{border-color:#FE2C55;background:#FFF5F7}
.layanan i{font-size:28px;margin-bottom:6px;display:block}
.layanan span{font-size:10px;font-weight:600;display:block}
.layanan[data-layanan='bike'] i{color:#E53935}
.layanan[data-layanan='car'] i{color:#1E88E5}
.layanan[data-layanan='belikan'] i{color:#FB8C00}
.layanan[data-layanan='belanjaan'] i{color:#43A047}
.layanan[data-layanan='antarkan'] i{color:#00ACC1}
.layanan[data-layanan='ambilkan'] i{color:#7CB342}
.layanan[data-layanan='travel'] i{color:#5E35B1}
.layanan[data-layanan='nota'] i{color:#8E24AA}
.btn-pesan{background:#FE2C55;color:#fff;width:calc(100% - 30px);margin:0 15px;padding:16px;border-radius:12px;font-size:16px;font-weight:700;border:none;text-transform:uppercase;cursor:pointer}
.btn-pesan:disabled{background:#E0E0E0;color:#9E9E9E}
.bottom-nav{position:fixed;bottom:0;left:0;right:0;background:#fff;border-top:1px solid #EEE;display:flex;z-index:100}
.nav-item{flex:1;text-align:center;padding:8px 5px;color:#9E9E9E;font-size:11px;cursor:pointer}
.nav-item.active{color:#FE2C55}
.nav-item i{display:block;font-size:20px;margin-bottom:2px}
.form-dinamis{display:none}
.form-dinamis.active{display:block}
.form-group{margin-bottom:12px}
.form-group label{font-size:12px;color:#757575;display:block;margin-bottom:4px}
.form-group input,.form-group textarea{width:100%;padding:12px;border:1px solid #E0E0E0;border-radius:8px}
.nota-item{background:#F5F5F5;padding:10px;border-radius:8px;margin-bottom:8px}
.nota-total{background:#FFF9C4;padding:12px;border-radius:8px;font-weight:700;text-align:right;margin-top:10px}
.modal{position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,.5);display:none;align-items:flex-end;z-index:999}
.modal.active{display:flex}
.modal-content{background:#fff;border-radius:20px 20px 0 0;width:100%;max-height:80vh;overflow-y:auto}
.modal-header{padding:15px;border-bottom:1px solid #eee;display:flex;justify-content:space-between;align-items:center;position:sticky;top:0;background:#fff}
</style>
</head>
<body>

<div class="header-wrap">
  <div class="header">
    <div class="logo"><span class="hitam">Kurir</span><span class="merah">Tiktok</span></div>
    <div class="kota" id="kota">Tanahgrogot</div>
  </div>
  <div class="status-bar" id="statusBar">BUKA - 08:00 s/d 21:00</div>
</div>

<div class="card">
  <div class="label">Nama</div>
  <input type="text" id="nama" placeholder="Nama kamu">
  <div class="label">No. WA</div>
  <input type="tel" id="wa" placeholder="08xxx">
</div>

<div class="info-bar">
  <div><i class="fa-solid fa-money-bill"></i> Cas || TF</div>
  <div class="jam" id="jamWita">--:-- WITA</div>
</div>

<div class="grid">
  <div class="layanan active" data-layanan="bike" onclick="pilihLayanan('bike')"><i class="fa-solid fa-motorcycle"></i><span>Bike</span></div>
  <div class="layanan" data-layanan="car" onclick="pilihLayanan('car')"><i class="fa-solid fa-car"></i><span>Car</span></div>
  <div class="layanan" data-layanan="belikan" onclick="pilihLayanan('belikan')"><i class="fa-solid fa-cart-shopping"></i><span>Belikan</span></div>
  <div class="layanan" data-layanan="belanjaan" onclick="pilihLayanan('belanjaan')"><i class="fa-solid fa-basket-shopping"></i><span>Belanjaan</span></div>
  <div class="layanan" data-layanan="antarkan" onclick="pilihLayanan('antarkan')"><i class="fa-solid fa-box"></i><span>Antarkan</span></div>
  <div class="layanan" data-layanan="ambilkan" onclick="pilihLayanan('ambilkan')"><i class="fa-solid fa-hand"></i><span>Ambilkan</span></div>
  <div class="layanan" data-layanan="travel" onclick="pilihLayanan('travel')"><i class="fa-solid fa-bus"></i><span>Travel</span></div>
  <div class="layanan" data-layanan="nota" onclick="bukaNota()"><i class="fa-solid fa-receipt"></i><span>Nota Digital</span></div>
</div>

<div id="form-container">
  <!-- Bike/Car -->
  <div class="form-dinamis active" id="form-bike">
    <div class="card">
      <div class="form-group"><label>Lokasi Jemput</label><input id="jemput" placeholder="Alamat jemput"></div>
      <div class="form-group"><label>Tujuan</label><input id="tujuan" placeholder="Alamat tujuan"></div>
    </div>
  </div>

  <!-- Belikan -->
  <div class="form-dinamis" id="form-belikan">
    <div class="card">
      <div class="form-group"><label>Beli di mana</label><input id="beliDimana" placeholder="Nama toko"></div>
      <div class="form-group"><label>Barang yang dibeli</label><textarea id="barangBelikan" placeholder="Contoh: Nasi goreng 2 porsi"></textarea></div>
      <div class="form-group"><label>Antar ke</label><input id="antarKe" placeholder="Alamat tujuan"></div>
    </div>
  </div>

  <!-- Belanjaan -->
  <div class="form-dinamis" id="form-belanjaan">
    <div class="card">
      <div class="form-group"><label>List Belanja</label><textarea id="listBelanja" placeholder="1. Beras 5kg&#10;2. Minyak 1L" rows="4"></textarea></div>
      <div class="form-group"><label>Antar ke</label><input id="antarBelanja" placeholder="Alamat tujuan"></div>
    </div>
  </div>

  <!-- Antarkan -->
  <div class="form-dinamis" id="form-antarkan">
    <div class="card">
      <div class="form-group"><label>Ambil dari</label><input id="ambilDari" placeholder="Alamat penjemputan"></div>
      <div class="form-group"><label>Antar ke</label><input id="antarKeAntarkan" placeholder="Alamat tujuan"></div>
      <div class="form-group"><label>Nama Penerima</label><input id="namaPenerima"></div>
      <div class="form-group"><label>WA Penerima</label><input id="waPenerima" type="tel"></div>
    </div>
  </div>

  <!-- Ambilkan -->
  <div class="form-dinamis" id="form-ambilkan">
    <div class="card">
      <div class="form-group"><label>Ambil di</label><input id="ambilDi" placeholder="Nama toko/kantor"></div>
      <div class="form-group"><label>Barang yang diambil</label><input id="barangAmbilkan"></div>
      <div class="form-group"><label>Antar ke</label><input id="antarKeAmbilkan"></div>
    </div>
  </div>

  <!-- Travel -->
  <div class="form-dinamis" id="form-travel">
    <div class="card">
      <div class="form-group"><label>Lokasi Jemput</label><input id="jemputTravel"></div>
      <div class="form-group"><label>Tujuan</label><input id="tujuanTravel"></div>
      <div class="form-group"><label>Jumlah Penumpang</label><input id="jumlahPenumpang" type="number" value="1"></div>
      <div class="form-group"><label>Catatan</label><textarea id="catatanTravel"></textarea></div>
    </div>
  </div>
</div>

<button class="btn-pesan" id="btnPesan" onclick="kirimOrder()">MEMESAN</button>

<div class="bottom-nav">
  <div class="nav-item active"><i class="fa-solid fa-circle-dot"></i><span>Beranda</span></div>
  <div class="nav-item"><i class="fa-solid fa-route"></i><span>Order</span></div>
  <div class="nav-item"><i class="fa-regular fa-star"></i><span>Favorit</span></div>
  <div class="nav-item"><i class="fa-solid fa-bars"></i><span>Menu</span></div>
</div>

<!-- Modal Nota -->
<div class="modal" id="modalNota">
  <div class="modal-content">
    <div class="modal-header">
      <div style="font-weight:700">Nota Digital</div>
      <div onclick="tutupNota()" style="font-size:24px;cursor:pointer">×</div>
    </div>
    <div style="padding:15px">
      <div class="form-group"><label>Nama Pelanggan</label><input id="notaNama"></div>
      <div class="form-group"><label>No WA Pelanggan</label><input id="notaWA" type="tel" placeholder="08xxx"></div>
      <div id="listItemNota"></div>
      <button class="btn-pesan" style="background:#4CAF50;margin:10px 0" onclick="tambahItemNota()">+ Tambah Item</button>
      <div class="nota-total">Total: Rp <span id="totalNota">0</span></div>
      <button class="btn-pesan" onclick="kirimNota()">Kirim Nota ke WA</button>
    </div>
  </div>
</div>

<script>
const config = {
  noWA: "6283137527300",
  kota: "Tanahgrogot",
  jamBuka: 8,
  jamTutup: 21,
  timezone: 8
};

let layananAktif = 'bike';
let itemNotaCount = 0;

function pilihLayanan(jenis){
  layananAktif = jenis;
  document.querySelectorAll('.layanan').forEach(el => el.classList.remove('active'));
  document.querySelector('[data-layanan="'+jenis+'"]').classList.add('active');
  document.querySelectorAll('.form-dinamis').forEach(el => el.classList.remove('active'));
  const form = document.getElementById('form-'+jenis);
  if(form) form.classList.add('active');
}

function updateJam(){
  const now = new Date();
  const utc = now.getTime() + (now.getTimezoneOffset() * 60000);
  const wita = new Date(utc + (3600000 * config.timezone));
  const jam = String(wita.getHours()).padStart(2,'0');
  const menit = String(wita.getMinutes()).padStart(2,'0');
  document.getElementById('jamWita').innerText = jam + ':' + menit + ' WITA';
  
  const jamNow = wita.getHours() + wita.getMinutes()/60;
  const statusBar = document.getElementById('statusBar');
  const btnPesan = document.getElementById('btnPesan');
  
  if(jamNow >= config.jamBuka && jamNow < config.jamTutup){
    statusBar.classList.remove('offline');
    statusBar.innerText = `BUKA - ${config.jamBuka}:00 s/d ${config.jamTutup}:00`;
    btnPesan.disabled = false;
  } else {
    statusBar.classList.add('offline');
    statusBar.innerText = `TUTUP - Buka jam ${config.jamBuka}:00 s/d ${config.jamTutup}:00`;
    btnPesan.disabled = true;
  }
}

function formatWA(no){
  let nomor = no.replace(/[^0-9]/g, '');
  if(nomor.startsWith('08')) return '62' + nomor.substring(1);
  if(nomor.startsWith('8')) return '62' + nomor;
  if(nomor.startsWith('62')) return nomor;
  return '62' + nomor;
}

function kirimOrder(){
  const nama = document.getElementById('nama').value.trim();
  const wa = document.getElementById('wa').value.trim();
  if(!nama || !wa) return alert('Isi nama dan WA dulu!');
  
  let pesan = `*ORDER BARU - ${layananAktif.toUpperCase()}*\n\n`;
  pesan += `Nama: ${nama}\nWA: ${wa}\n\n`;
  
  if(layananAktif == 'bike' || layananAktif == 'car'){
    const jemput = document.getElementById('jemput').value;
    const tujuan = document.getElementById('tujuan').value;
    if(!jemput || !tujuan) return alert('Isi lokasi jemput dan tujuan!');
    pesan += `Jemput: ${jemput}\nTujuan: ${tujuan}`;
  }
  else if(layananAktif == 'belikan'){
    const beli = document.getElementById('beliDimana').value;
    const barang = document.getElementById('barangBelikan').value;
    const antar = document.getElementById('antarKe').value;
    if(!beli || !barang || !antar) return alert('Lengkapi semua data!');
    pesan += `Beli di: ${beli}\nBarang: ${barang}\nAntar ke: ${antar}`;
  }
  else if(layananAktif == 'belanjaan'){
    const list = document.getElementById('listBelanja').value;
    const antar = document.getElementById('antarBelanja').value;
    if(!list || !antar) return alert('Lengkapi data!');
    pesan += `List Belanja:\n${list}\nAntar ke: ${antar}`;
  }
  else if(layananAktif == 'antarkan'){
    const ambil = document.getElementById('ambilDari').value;
    const antar = document.getElementById('antarKeAntarkan').value;
    const penerima = document.getElementById('namaPenerima').value;
    const waPenerima = document.getElementById('waPenerima').value;
    if(!ambil || !antar || !penerima || !waPenerima) return alert('Lengkapi data!');
    pesan += `Ambil dari: ${ambil}\nAntar ke: ${antar}\nPenerima: ${penerima}\nWA Penerima: ${waPenerima}`;
  }
  else if(layananAktif == 'ambilkan'){
    const ambil = document.getElementById('ambilDi').value;
    const barang = document.getElementById('barangAmbilkan').value;
    const antar = document.getElementById('antarKeAmbilkan').value;
    if(!ambil || !barang || !antar) return alert('Lengkapi data!');
    pesan += `Ambil di: ${ambil}\nBarang: ${barang}\nAntar ke: ${antar}`;
  }
  else if(layananAktif == 'travel'){
    const jemput = document.getElementById('jemputTravel').value;
    const tujuan = document.getElementById('tujuanTravel').value;
    const jumlah = document.getElementById('jumlahPenumpang').value;
    const catatan = document.getElementById('catatanTravel').value;
    if(!jemput || !tujuan || !jumlah) return alert('Lengkapi data!');
    pesan += `Jemput: ${jemput}\nTujuan: ${tujuan}\nPenumpang: ${jumlah} orang`;
    if(catatan) pesan += `\nCatatan: ${catatan}`;
  }
  
  pesan += '\n\nMetode Bayar: Cas || TF';
  window.open('https://wa.me/'+config.noWA+'?text='+encodeURIComponent(pesan), '_blank');
}

function bukaNota(){
  document.getElementById('modalNota').classList.add('active');
}
function tutupNota(){
  document.getElementById('modalNota').classList.remove('active');
}

function tambahItemNota(){
  itemNotaCount++;
  const div = document.createElement('div');
  div.className = 'nota-item';
  div.innerHTML = `<input placeholder="Nama barang" id="item${itemNotaCount}">
    <div style="display:flex;gap:8px;margin-top:8px">
      <input type="number" placeholder="Harga" id="harga${itemNotaCount}" oninput="hitungTotal()">
      <input type="number" placeholder="Qty" id="qty${itemNotaCount}" value="1" oninput="hitungTotal()">
    </div>`;
  document.getElementById('listItemNota').appendChild(div);
}

function hitungTotal(){
  let total = 0;
  for(let i=1; i<=itemNotaCount; i++){
    const harga = parseInt(document.getElementById('harga'+i)?.value || 0);
    const qty = parseInt(document.getElementById('qty'+i)?.value || 0);
    total += harga * qty;
  }
  document.getElementById('totalNota').innerText = total.toLocaleString('id-ID');
}

function kirimNota(){
  const nama = document.getElementById('notaNama').value;
  const wa = document.getElementById('notaWA').value;
  if(!nama || !wa) return alert('Lengkapi nama & WA pelanggan!');
  
  let pesan = `*NOTA DIGITAL - KurirTiktok*\n\nPelanggan: ${nama}\n\n`;
  let total = 0;
  for(let i=1; i<=itemNotaCount; i++){
    const item = document.getElementById('item'+i)?.value;
    const harga = parseInt(document.getElementById('harga'+i)?.value || 0);
    const qty = parseInt(document.getElementById('qty'+i)?.value || 0);
    if(item){
      const subtotal = harga * qty;
      total += subtotal;
      pesan += `${item} x${qty} = Rp ${subtotal.toLocaleString('id-ID')}\n`;
    }
  }
  pesan += `\n*TOTAL: Rp ${total.toLocaleString('id-ID')}*\n\nTerima kasih 🙏`;
  window.open('https://wa.me/'+formatWA(wa)+'?text='+encodeURIComponent(pesan), '_blank');
  tutupNota();
}

document.getElementById('kota').innerText = config.kota;
updateJam();
setInterval(updateJam, 1000);
</script>
</body>
</html>
