# <!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ucapan Lebaran Interaktif</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-image: url('background.jpg'); /* Ganti dengan jalur gambar Anda jika berbeda */
            background-size: cover;
            background-repeat: no-repeat;
            transition: background-image 1s ease-in-out;
        }
        .slide {
            text-align: center;
            padding: 40px;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            width: 80%;
            max-width: 600px;
            margin: 20px;
        }
        button {
            padding: 10px 20px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background-color: #ffab40;
            color: white;
        }
        #nggak {
            position: relative;
        }
        input[type="text"] {
            padding: 10px;
            margin: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .whatsapp-link {
            display: block;
            margin-top: 20px;
            padding: 10px 20px;
            background-color: #25d366;
            color: white;
            text-decoration: none;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="slide" id="slide1">
        <h2>Halo semuanya!</h2>
        <p>Nama kamu siapa?</p>
        <input type="text" id="nama" placeholder="Masukkan nama kamu">
        <button id="lanjut1">Lanjut</button>
    </div>

    <div class="slide" id="slide2" style="display: none;">
        <h2>Mohon Maaf Lahir dan Batin, <span id="nama2"></span>!</h2>
        <p>Jika ada salah kata atau perbuatan, mohon dimaafkan.</p>
        <button id="lanjut2">Lanjut</button>
    </div>

    <div class="slide" id="slide3" style="display: none;">
        <h2>Mumpung Lebaran... THR dong, <span id="nama3"></span>!</h2>
        <button id="iya">Iya!</button>
        <button id="nggak" onmouseover="this.style.left = (Math.random() * 50 - 25) + 'px'; this.style.top = (Math.random() * 50 - 25) + 'px';">Nggak!</button>
        <button id="lanjut3">Lanjut</button>
    </div>

    <div class="slide" id="slide4" style="display: none;">
        <h2>Hehe, bercanda kok, <span id="nama4"></span>!</h2>
        <p>Yang penting silaturahmi tetap terjaga, sampai ketemu lebaran selanjutnya.</p>
        <p>Sekali lagi, mohon maaf lahir dan batin dan minal aidin wal faizin!</p>
        <a href="https://wa.me/6285161123017?text=Selamat%20Lebaran%20ya!" class="whatsapp-link" target="_blank">Kirim Pesan WhatsApp</a>
    </div>

    <script>
        var slideIndex = 1;
        var slides = ['slide1', 'slide2', 'slide3', 'slide4'];

        function showSlide(n) {
            slides.forEach(slide => document.getElementById(slide).style.display = 'none');
            document.getElementById(slides[n - 1]).style.display = 'block';
        }

        showSlide(slideIndex);

        document.getElementById('lanjut1').addEventListener('click', function() {
            var nama = document.getElementById('nama').value;
            if (nama) {
                document.getElementById('nama2').textContent = nama;
                document.getElementById('nama3').textContent = nama;
                document.getElementById('nama4').textContent = nama;
                slideIndex++;
                showSlide(slideIndex);
            } else {
                alert('Masukkan nama kamu dulu ya!');
            }
        });

        document.getElementById('lanjut2').addEventListener('click', function() {
            slideIndex++;
            showSlide(slideIndex);
        });

        document.getElementById('lanjut3').addEventListener('click', function() {
            slideIndex++;
            showSlide(slideIndex);
        });

        document.getElementById('iya').addEventListener('click', function() {
            alert('Alhamdulillah, terima kasih!');
        });
    </script>
</body>
</html>
