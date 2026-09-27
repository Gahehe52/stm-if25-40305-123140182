# Tugas 2 — Analisis Sinyal Suara & Noise Statis

## Identitas
- **Nama:** Muhammad Ghama Al Fajri
- **NIM:** 123140182

## Tentang Rekaman
- **Perangkat rekam:** Smartphone, direkam sambil duduk ±0.5–1 meter di depan sumber noise.
- **Sumber noise statis:** Kipas laptop.
- **Isi rekaman:** Pembacaan beberapa kalimat dari artikel berita, hampir di sepanjang durasi rekaman.
- **Durasi:** 20.08 detik.
- **Laju sampel asli:** 44100 Hz.
- **Format:** WAV (PCM, uncompressed).

## Isi Folder
| Berkas | Keterangan |
|---|---|
| `tugas_audio_noise_statis.ipynb` | Notebook lengkap: metadata audio, visualisasi 4 dimensi (waveform, FFT, STFT, Mel-spektrogram), serta eksperimen resampling & pembuktian aliasing. |
| `tugas_02_audio_noise_statis_<NIM>.pdf` | Hasil ekspor PDF dari notebook yang sudah dijalankan penuh. |
| `audio_original.wav` | Rekaman suara asli (berita + noise kipas laptop). |
| `audio_downsampled_naive.wav` | Hasil downsampling ke 8000 Hz tanpa filter anti-aliasing (naive decimation) — terjadi aliasing. |
| `audio_downsampled_clean.wav` | Hasil downsampling ke 8000 Hz dengan filter anti-aliasing (`librosa.resample`) — bebas aliasing. |

## Ringkasan Temuan
- Frekuensi dominan noise statis (kipas laptop) berada di sekitar **128 Hz**.
- Noise statis tampak sebagai pita horizontal konstan pada spektrogram STFT, kontras dengan pola naik-turun suara bicara.
- Pada downsampling ke 8000 Hz tanpa filter (naive decimation), terjadi aliasing yang terbukti dari energi berlebih pada pita frekuensi 1500–4000 Hz (rasio ±1.33× dibanding hasil resampling terfilter).

## Cara Menjalankan
1. Pastikan `audio_original.wav` berada di folder yang sama dengan notebook.
2. Jalankan seluruh sel notebook secara berurutan (`Run All`).
3. Seluruh visualisasi dan berkas audio hasil eksperimen akan otomatis ter-generate.