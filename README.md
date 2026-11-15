# TA-06 Dinamika Tangki Air dengan Lubang Bocor

Tugas Akhir 06 - Pemodelan dan Simulasi (Dynamic System Modelling)

Simulasi tinggi air pada tangki yang diisi dari kran dan bocor melalui lubang di dasarnya.
Model berupa ODE orde-1 nonlinier yang diselesaikan dengan metode Euler.

    A * dh/dt = Q_in(t) - k * sqrt(h)

| Simbol | Keterangan | Nilai |
|---|---|---|
| A | Luas penampang tangki | 0.20 m^2 |
| Q_in | Debit masuk (sinyal kontrol) | 0.00015 m^3/s (basis) |
| k | Konstanta aliran keluar | 0.0003 m^2.5/s |
| h(0) | Tinggi awal | 0.05 m |
| h_max | Tinggi maksimum tangki | 0.60 m |
| dt | Langkah waktu | 1 s |

## Struktur folder

    TA_Dinamika_Tangki_Air/
    |-- main.py                      # program utama (jalankan ini)
    |-- TA_Dinamika_Tangki_Air.ipynb # versi notebook (Jupyter / Google Colab)
    |-- requirements.txt
    |-- README.md
    `-- hasil_simulasi/              # grafik hasil (dibuat otomatis)

## Cara menjalankan

Butuh Python 3.10 atau lebih baru.

    pip install -r requirements.txt
    python main.py

Grafik tersimpan di folder `hasil_simulasi/`. Versi notebook dapat dibuka di Jupyter atau
Google Colab (unggah file `.ipynb`, lalu Runtime > Run all).

## Isi simulasi

1. **Steady state**: Q_in konstan, h menuju (Q_in/k)^2 = 0.25 m.
2. **Step**: Q_in naik ke 0.0002 m^3/s pada menit ke-60, h menuju 0.4444 m.
3. **Impuls**: pulsa Q_in 0.0008 m^3/s selama 60 s, h melonjak lalu kembali ke 0.25 m.
4. **Ramp**: Q_in naik linear selama 30 menit, h naik landai dan tertinggal.
5. **Sinusoida**: Q_in berosilasi, h berosilasi dengan amplitudo teredam dan fase tertinggal.

## Hasil utama

| Simulasi | Hasil |
|---|---|
| Steady state | h akhir 0.249997 m (teori 0.25 m) |
| Step | h akhir 0.4414 m (teori steady state baru 0.4444 m) |
| Impuls | h puncak 0.4368 m, lalu menurun kembali ke 0.25 m |
| Ramp | h akhir 0.4342 m |
| Sinusoida | h berosilasi 0.187 - 0.337 m |

## Tautan

- Laporan Project dan Tutorial: (isi)
- Video tutorial YouTube: (isi)
