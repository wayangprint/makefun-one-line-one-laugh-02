# BUILD REPORT — makefun-one-line-one-laugh-01

## Kompetisi

- Slug: `u-deysumbrella-one-line-one-laugh-e0cdcda9`
- Judul: "One Line, One Laugh"
- Hadiah: $2 winner-takes-all, tutup 26 Nov 2026 23:10 WIB
- Repo GitHub (dibuat parent): `wayangprint/makefun-one-line-one-laugh-01`

## Batas karakter RULES (menang atas angka tugas)

- RULES.txt kit, bagian "The gate": entri adalah **1–140 karakter** UTF-8, bukan hanya
  whitespace. Sama dengan angka 140 dari tugas — RULES yang dipakai.
- Baris entri: **97 karakter** — di dalam rentang 1–140.

## Teks entri (persis, satu baris)

> My toaster filed a complaint, apparently popping up unannounced every morning counts as stalking.

- Jumlah karakter: 97 (dihitung dengan `wc -m`, terverifikasi; murni ASCII, jadi
  sama dengan jumlah byte)
- sha256 entry.txt: `04c524a3d29820b1a600875db975ad775db5dcc93f80f88d4df8915e26843fdd`
- Tanpa newline di akhir file entry.txt (terverifikasi dengan `od -c`).

## Program

- `main.ts` — Node 22, stdlib saja, tanpa network/random/clock. Menulis satu baris
  ke entry.txt (hormat `MAKEFUN_OUTPUT_DIR`, fallback `/output` bila ada, kalau
  tidak di samping script) + echo ke stdout. Guard `guardLength` menolak
  menulis bila panjang di luar 1–140 karakter.
- Revisi (thinking_revised): setelah main.ts pertama jalan, dilakukan revisi nyata
  — struktur diubah dari konstanta SETUP/TWIST + `buildLine`/`resolveOutputDir`/
  `writeEntry` menjadi objek `jokeBeats` + `buildJokeLine`/`guardLength`/
  `resolveOutput`/`emitLine`, plus komentar baru. Bukan sekadar ganti string.
  (Revisi ini juga mengganti em dash pada baris entri menjadi koma, sehingga
  entri murni ASCII: 97 karakter = 97 byte.)

## Verifikasi determinisme (2x run)

- Run 1: `MAKEFUN_OUTPUT_DIR=/tmp/scratch-olla node main.ts`
- Run 2: `MAKEFUN_OUTPUT_DIR=/tmp/scratch-ollb node main.ts`
- sha256 kedua entry.txt: `04c524a3d29820b1a600875db975ad775db5dcc93f80f88d4df8915e26843fdd`
  (identik dengan entry.txt di repo) — `cmp` mengonfirmasi byte-identik.

## Kit

- Kit: `~/workspace/superteam-raenest/makefun/one-line-one-laugh-01/kit/`
- kit.json `bundle_sha256`: `66f66e8513a28a1527ee9549be1220faf104983ebf249b5d709195e2fa680f74`
- sha256 tarball kit (artefak berbeda dari bundle_sha256):
  `935ef45b4ef46f495eaad56db93221a13b8d9b6d2e97cadb26aed69ca8951dd0`

## Commit lokal

- Commit SHA (entry commit): `6e4c7cef660810b06ee17cf8fdd4a717a1d37399`
  (file: main.ts, entry.txt, README.md, LICENSE, .makefun/owner.json,
  requirements.json, BUILD-REPORT.md, prompt.txt). BUILD-REPORT.md kemudian
  diperbarui dengan SHA ini dalam commit lanjutan — lihat `git log` untuk
  HEAD final.

## Daftar file

- `main.ts`
- `entry.txt`
- `README.md`
- `LICENSE` (MIT, baris pertama `SPDX-License-Identifier: MIT`)
- `.makefun/owner.json` (wallet `2cy7DSBQwGoXa3w7qEr9VgtxhjLCF8KqpCRc3opcpFTt`)
- `requirements.json`
- `BUILD-REPORT.md`
- `prompt.txt`
