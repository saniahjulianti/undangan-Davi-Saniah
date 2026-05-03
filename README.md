<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Undangan Pernikahan</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', sans-serif;
    overflow-x: hidden;
}

/* COVER */
#cover {
    height: 100vh;
    background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
                url('s.jpeg') center/cover no-repeat;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    padding: 40px 20px;
    color: white;
}

.top-text {
    text-align: center;
}

.top-text h1 {
    font-size: 32px;
    color: #ff4d6d;
}

/* CARD */
.card {
    background: rgba(255,255,255,0.95);
    padding: 20px;
    border-radius: 20px;
    text-align: center;
    width: 95%;
    max-width: 350px;
    color: black;
}

/* BUTTON */
button {
    margin-top: 15px;
    background: #8b0000;
    color: white;
    border: none;
    padding: 12px;
    border-radius: 12px;
    width: 100%;
}

/* CONTENT */
#content {
    display: none;
    padding: 20px;

    background: 
        linear-gradient(rgba(255,255,255,0.85), rgba(255,255,255,0.9)),
        url('bunga.jpg') center/cover no-repeat;

    min-height: 100vh;
}

/* SECTION */
.section {
    text-align: center;
    margin: 30px 0;
}

/* MEMPELAI */
.mempelai {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
}

.box {
    background: white;
    padding: 15px;
    border-radius: 20px;
    width: 95%;
    max-width: 320px;
    text-align: center;
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
}

/* FOTO RESPONSIVE */
.box img {
    width: 35vw;
    max-width: 120px;
    aspect-ratio: 1/1;
    object-fit: cover;
    border-radius: 50%;
    border: 4px solid #ff4d6d;
    margin-bottom: 10px;
}

/* DATE BOX */
.date-box {
    background: rgba(255,255,255,0.95);
    padding: 20px;
    border-radius: 25px;
    text-align: center;
    margin: 20px 0;
    box-shadow: 0 10px 25px rgba(0,0,0,0.15);
}

.title {
    font-family: cursive;
    color: #8b0000;
    margin-bottom: 20px;
}

/* GRID */
.time-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
}

/* BULAT */
.circle {
    width: 55px;
    height: 55px;
    border: 2px solid black;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 16px;
    margin: auto;
}

/* CARD2 */
.card2 {
    background: white;
    padding: 15px;
    border-radius: 20px;
    margin-bottom: 15px;
    text-align: center;
}

/* INPUT */
input, textarea {
    width: 95%;
    padding: 10px;
    margin: 5px;
    border-radius: 10px;
    border: 1px solid #ccc;
}

/* RESPONSIVE */
@media (max-width: 480px) {
    .top-text h1 {
        font-size: 26px;
    }

    .circle {
        width: 50px;
        height: 50px;
        font-size: 14px;
    }

    button {
        font-size: 14px;
    }
}

/* KOTAK KATA-KATA (LEBIH SOLID) */
.quote-box {
    background: white; /* ini bikin kolom jelas */
    padding: 20px;
    border-radius: 20px;
    text-align: center;
    margin: 20px 0;
    box-shadow: 0 8px 20px rgba(0,0,0,0.15);
}

/* TEKS */
.quote-box p {
    font-style: italic;
    font-size: 15px;
    color: #333;
    line-height: 1.6;
    margin-bottom: 10px;
}

.quote-box h4 {
    color: #8b0000;
    font-weight: normal;
}

/* GALERI GRID */
/* GANTI CSS GALERI LAMA JADI INI */

.gallery{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:14px;
    margin-bottom:20px;
}

.gallery img{
    width:100%;
    height:220px;
    object-fit:contain;   /* biar foto full keliatan */
    object-position:center;
    background:#fff;
    border-radius:20px;
    padding:8px;
    cursor:pointer;
    transition:0.4s;
    box-shadow:0 8px 20px rgba(0,0,0,0.08);
}

.gallery img:hover{
    transform:scale(1.03);
}

/* HP */
@media(max-width:480px){
.gallery{
    grid-template-columns:1fr;
}

.gallery img{
    height:240px;
}
}

/* MODAL (ZOOM) */
#modal {
    display: none;
    position: fixed;
    z-index: 999;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.8);
    justify-content: center;
    align-items: center;
}

#modal img {
    width: 90%;
    max-width: 400px;
    border-radius: 20px;
}

/* BUTTON MUSIK */
.music-btn {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background: #8b0000;
    color: white;
    font-size: 20px;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
    z-index: 999;
}

/* ANIMASI PUTAR */
.music-btn.playing {
    animation: putar 3s linear infinite;
}

@keyframes putar {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}

/* LOKASI */
.lokasi-box{
    background: rgba(255,255,255,0.95);
    padding: 25px;
    border-radius: 25px;
    text-align:center;
    margin:20px 0;
}

.lokasi-title{
    font-family:cursive;
    color:#8b0000;
    font-size:38px;
    margin-bottom:15px;
}

.lokasi-nama{
    font-size:42px;
    margin-top:18px;
    margin-bottom:10px;
}

.lokasi-alamat{
    font-size:18px;
    line-height:1.8;
    color:#333;
    margin-bottom:20px;
}

.lokasi-btn{
    background:#8b0000;
    color:white;
    border:none;
    padding:14px 28px;
    border-radius:30px;
    font-size:18px;
}

/* HADIAH */
.hadiah-box{
    background: rgba(255,255,255,0.92);
    padding: 25px 20px;
    border-radius: 25px;
    text-align:center;
    margin:20px 0;
}

.hadiah-title{
    font-family:cursive;
    color:#8b0000;
    font-size:34px;
    margin-bottom:15px;
}

.hadiah-text{
    color:#333;
    font-size:15px;
    line-height:1.8;
    margin-bottom:20px;
}

.hadiah-btn-wrap{
    display:flex;
    gap:10px;
    justify-content:center;
}

.hadiah-btn{
    background:#8b0000;
    color:white;
    border:none;
    padding:12px 18px;
    border-radius:30px;
    width:auto;
    min-width:120px;
    font-size:14px;
}

/* REKENING */
.rekening-box{
    background:#fff;
    border:2px solid #8b0000;
    border-radius:18px;
    padding:15px;
    margin-bottom:12px;
    color:#333;
    line-height:1.7;
}
/* ACARA */
.acara-box{
    padding:25px 20px;
    border-radius:25px;
    text-align:center;
}

.acara-title{
    font-family:cursive;
    font-size:34px;
    color:#8c1d2c;
    margin-bottom:18px;
}

.acara-item{
    display:flex;
    align-items:center;
    gap:10px;
    background:#fff;
    padding:12px;
    border-radius:15px;
    margin-bottom:10px;
    border:1px solid #f0d6d9;
}

.acara-item span{
    font-size:22px;
}

.acara-item p{
    margin:0;
    font-size:16px;
    color:#4b3a34;
}

.acara-btn{
    margin-top:15px;
    background:#8c1d2c;
    color:#fff;
    border:none;
    padding:12px;
    border-radius:30px;
}
</style>


</head>

<body>

<!-- COVER -->
<div id="cover">
    <div class="top-text">
        <h2>The Wedding Of</h2>
        <h1>Saniah & Davi</h1>
    </div>

    <div class="card">
        <p>Kepada Yth.</p>
        <p>Bapak/Ibu/Saudara/i</p>
        <p id="namaTamu">Tamu Undangan</p>

        <button onclick="bukaUndangan()">Open Invitation</button>
    </div>
</div>

<!-- CONTENT -->
<div id="content">

    <!-- KATA KATA -->
    <div class="section">
        <h2>The Wedding Of</h2>
    </div>
        <div class="quote-box">
            <h5>Davi & Saniah</h5>
        <p>
            "Dan di antara tanda-tanda kebesaran-Nya, 
            Dia menciptakan pasangan hidup agar kamu menemukan ketenangan di dalamnya, 
            serta menjadikan cinta dan kasih sayang di antara kalian."
        </p>
        <h4>QS. Ar-Rum: 21</h4>
    </div>

    <div class="mempelai">

        <div class="box">
            <img src="davi.jpeg">
            <h3>Davi</h3>
            <p>Putra dari</p>
            <p>Bapak Uus Lustiawan & Ibu Nunung Nurhayati</p>
        </div>
         <div class="box">
            <img src="sani.jpeg">
            <h3>Saniah</h3>
            <p>Putri dari</p>
            <p>Bapak Aris & Ibu Kelly Aprilla</p>
        </div>
    </div>

    <!-- GALERI -->
    <div class="section">
    </div>

    <div class="gallery">

        <img src="1.jpeg" onclick="openModal(this)">
        <img src="2.jpeg" onclick="openModal(this)">
        <img src="3.jpeg" onclick="openModal(this)">
        <img src="4.jpeg" onclick="openModal(this)">

    </div>

    <!-- MODAL ZOOM -->
    <div id="modal" onclick="closeModal()">
        <img id="modal-img">
    </div>

    <!-- MASUKKAN DI BAWAH BAGIAN ACARA -->

    <!-- LOKASI -->
   <!-- LOKASI STYLE ELEGAN -->
    <div class="card2 lokasi-box">

        <h2 class="lokasi-title">Lokasi Acara</h2>

      <iframe
        src="https://www.google.com/maps?q=Bitung+Sari+Ciawi+Bogor&output=embed"
        width="100%"
        height="220"
        style="border:3px solid #8b0000; border-radius:18px;"
        allowfullscreen=""
        loading="lazy">
        </iframe>

        <!-- TOMBOL LINK ASLI -->
        <a href="https://maps.app.goo.gl/Na9yKscP5cigKwJb9" target="_blank">
            <button class="lokasi-btn">Buka Google Maps</button>
        </a>


        <p class="lokasi-alamat">
            Jl. Mayjen He Sukma<br>
            Ds. Bitung Sari Kp. Bitung Ratna rt01/02 Kec. Ciawi Kab. Bogor<br>
            Jawa Barat 16720
        </p>


    </div>
    <!-- HADIAH -->
   
    <!-- HADIAH PERNIKAHAN -->
<!-- GANTI BAGIAN HADIAH LAMA DENGAN INI -->
<div class="card2 hadiah-box">

    <h2 class="hadiah-title">Hadiah Pernikahan</h2>

    <p class="hadiah-text">
        Doa dan Restu Anda sangat berarti bagi kami.<br>
        Namun, jika memberi adalah cara Anda<br>
        mengungkapkan kasih sayang, kami akan<br>
        menerimanya dengan senang hati, karena itu<br>
        akan menambah kebahagiaan kami.
    </p>

    <div class="rekening-box">
        <p><b>BCA</b></p>
        <p>6821846801</p>
        <p>a.n Davi</p>
    </div>

    <div class="rekening-box">
        <p><b>BCA</b></p>
        <p>6821989393</p>
        <p>a.n Saniah</p>
    </div>

</div>

   
    <!-- COUNTDOWN -->
    <div class="date-box">
        <h2 class="title">Date</h2>

        <div class="time-grid">
            <div>
                <div class="circle" id="day">00</div>
                <p>Day</p>
            </div>
            <div>
                <div class="circle" id="hour">00</div>
                <p>Hour</p>
            </div>
            <div>
                <div class="circle" id="minute">00</div>
                <p>Minute</p>
            </div>
            <div>
                <div class="circle" id="second">00</div>
                <p>Second</p>
            </div>
        </div>

        <button>Save the Date</button>
    </div>

    <!-- ACARA -->
   <!-- GANTI BAGIAN ACARA LAMA DENGAN INI -->

    <div class="card2 acara-box">

        <h2 class="acara-title">Save The Date</h2>

        <div class="acara-item">
            <span>📅</span>
            <p>Minggu, 31 Mei 2026</p>
        </div>

        <div class="acara-item">
            <span>⏰</span>
            <p>09.00 WIB - Selesai</p>
        </div>

        <div class="acara-item">
            <span>📍</span>
            <p>Gedung Serbaguna</p>
        </div>

        <button class="acara-btn">Kami Menanti Kehadiran Anda</button>

    </div>

    <!-- UCAPAN -->
    <div class="card2">
        <h3>💌 Ucapan</h3>
        <input type="text" placeholder="Nama">
        <textarea placeholder="Tulis ucapan..."></textarea>
        <button>Kirim</button>
    </div>

    <!-- TAMBAHKAN DI PALING BAWAH SEBELUM </div> CONTENT -->

    <div class="card2 penutup-box">

        <h2 class="penutup-title">Terima Kasih</h2>

        <p class="penutup-text">
            Merupakan suatu kehormatan dan kebahagiaan bagi kami<br>
            apabila Bapak/Ibu/Saudara/i berkenan hadir dan<br>
            memberikan doa restu kepada kami.
        </p>

        <h3 class="penutup-nama">Davi & Saniah</h3>

    </div>

    <!-- AUDIO -->
    <audio id="musik" loop>
        <source src="tiara.mp3" type="audio/mpeg">
    </audio>

    <!-- BUTTON MUSIK -->
    <div class="music-btn" onclick="toggleMusic()">
        ▶️
    </div>

</div>

<script>
// OPEN
let isPlaying = false;

function bukaUndangan() {
    document.getElementById("cover").style.display = "none";
    document.getElementById("content").style.display = "block";

    const musik = document.getElementById("musik");

    musik.play().then(() => {
        isPlaying = true;
        document.querySelector(".music-btn").innerHTML = "⏸️";
        document.querySelector(".music-btn").classList.add("playing");
    }).catch(() => {
        console.log("Autoplay gagal");
    });
}

// NAMA TAMU
const params = new URLSearchParams(window.location.search);
const nama = params.get("nama");
if (nama) document.getElementById("namaTamu").innerText = nama;

// COUNTDOWN
const targetDate = new Date("2026-05-31T09:00:00").getTime();

setInterval(() => {
    const now = new Date().getTime();
    const diff = targetDate - now;

    const d = Math.floor(diff / (1000*60*60*24));
    const h = Math.floor((diff % (1000*60*60*24)) / (1000*60*60));
    const m = Math.floor((diff % (1000*60*60)) / (1000*60));
    const s = Math.floor((diff % (1000*60)) / 1000);

    document.getElementById("day").innerText = d;
    document.getElementById("hour").innerText = h;
    document.getElementById("minute").innerText = m;
    document.getElementById("second").innerText = s;

}, 1000);

// OPEN FOTO
function openModal(img) {
    document.getElementById("modal").style.display = "flex";
    document.getElementById("modal-img").src = img.src;
}

// CLOSE FOTO
function closeModal() {
    document.getElementById("modal").style.display = "none";
}
</script>

</body>
</html>
