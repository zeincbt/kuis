<!DOCTYPE html>
<body>

<div id="formulir">

<h1>Formulir tubuh</h1>

<html>
<head>
    <title>Formulir dan Kuis</title>

    <script>
        let soal = [
            { tanya: "Organ yang memompa darah ke seluruh tubuh?", jawab: "jantung" },
            { tanya: "Organ yang digunakan untuk bernapas?", jawab: "paru paru" },
            { tanya: "Pusat kendali tubuh manusia?", jawab: "otak" },
            { tanya: "Organ yang menyaring darah?", jawab: "ginjal" },
            { tanya: "Sel darah merah membawa?", jawab: "oksigen" },
            { tanya: "Organ terbesar pada tubuh manusia?", jawab: "kulit" },
            { tanya: "Pencernaan makanan dimulai di?", jawab: "mulut" },
            { tanya: "Organ yang menghasilkan empedu?", jawab: "hati" },
            { tanya: "Organ setelah lambung adalah?", jawab: "usus halus" },
            { tanya: "Pembuluh darah yang membawa darah keluar dari jantung?", jawab: "arteri" }
        ];

        let nomor = 0;

        function lanjut() {
            document.getElementById("formulir").style.display = "none";
            document.getElementById("kuis").style.display = "block";
            tampilSoal();
        }

        function tampilSoal() {
            document.getElementById("pertanyaan").innerHTML =
                "Soal " + (nomor + 1) + " : " + soal[nomor].tanya;

            document.getElementById("jawaban").value = "";
            document.getElementById("hasil").innerHTML = "";
        }

        function cekJawaban() {
            let jawaban = document.getElementById("jawaban").value.toLowerCase().trim();

            if (jawaban == soal[nomor].jawab) {
                document.getElementById("hasil").innerHTML = "Kamu benar!";

                nomor++;

                if (nomor < soal.length) {
                    setTimeout(tampilSoal, 1000);
                } else {
                    document.getElementById("kuis").innerHTML =
                        "<h2>Selamat!</h2><p>Anda telah menyelesaikan semua soal.</p>";
                }

            } else {
                document.getElementById("hasil").innerHTML =
                    "Jawaban salah. Silakan coba lagi.";
            }
        }
    </script>
</head>

<form>

Nama.....:
<input type="text"><br><br>

Email.....:
<input type="email"><br><br>

Password:
<input type="password"><br><br>

Umur......:
<input type="number"><br><br>

<h4>Harap isi formulir ini agar bisa</h4>
<h4>melanjutkan ke lembar selanjutnya.</h4>

<button type="button" onclick="lanjut()">
Kirim Formulir Ini
</button>

</form>

</div>

<div id="kuis" style="display:none;">

<h2>Kuis Cara Kerja Tubuh Manusia</h2>

<p id="pertanyaan"></p>

<input type="text" id="jawaban" placeholder="Masukkan jawaban">

<button type="button" onclick="cekJawaban()">
Kirim Jawaban
</button>

<p id="hasil"></p>

</div>

</body>
</html>
