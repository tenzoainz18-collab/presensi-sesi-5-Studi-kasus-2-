1.Import library
random=untuk membuat angka acak
matplotlib.pyplot=untuk menampilkan grafik perkembangan solusi.

2.Data barang dan parameter
pada bagian data dan parameter berisi data items adalah daftar barang memiliki atribut nama,berat,dan nilai.dan parameter MAX_WEIGHT sebagai kapasistas.POP_SIZE sebagai jumlah individu dalam satu populasi.GENERATIONS sebagai jumlah iterasi evolusi.MUTATION_RATE sebagai peluang mutasi pada gen,dan ELITE_SIZE adalah jumlah invidu terbaik yang langsung dipertahankan.

3.Inisialisasi
pada bagian Inisialisasi terdapat fungsi create_individual() yang berfungsi membuat satu individu berupa representasi biner yaitu 0 dan 1 sepanjang jumlah item.nilai 1 =dipilih dan 0 = tidak dipilih.fungsi init_population() digunakan untuk populasi awal yang terdiri dari sejumlah individu sebagai POP_SIZE.menjadi titik awal evolusi.

4.Fitness(penilaian)
Fungsi fitness() untuk menilai kualitas setiap invidu.dengan cara menjumlahkan total berat dan total nilai dari barang yang dipilih berdasarkan representasi biner individu.jika total berat melebihi MAX_WEIGHT,maka individu dianggap tidak valid dan nilai fitnessnya 0 sebagai penalti.jika tidak melebihi,maka fitness sama dengan total nilai barang,maka solusi dengan nilai terbesar akan dianggap terbaik.

5.Selection(seleksi)
Fungsi selection() bertugas memilih individu yang akan menjadi induk dalam proses reproduksi.metode yang digunakan adalah tournament selection,yaitu dengan mengambil 3 individu secara acak dari populasi,lalu memilih individu dengan fitness terbaik.cara ini membantu menjaga keseimbangan antara eksplorasi dan ekploitasi solusi.

6.Crossover(persilangan)
Fungsi crossover() digunakan untuk menggabungkan dua individu parent(p) menjadi satu individu baru.proses dilakukan dengan memilih titik potong secara acak,kemudia menggabungkan sebagian gen dari parent pertama dan sebagian dari parent kedua.tujuan adalah menggabungkan kelebihan dari dua solusi.

7.Mutation(mutasi)
fungsi mutate() berfungsi untuk menambahkan variasi dalam populasi dengan cara mengubah gen secara acak berdasarkan MUTATION_RATE.jika suatu gen terkena mutasi,maka nilainya dibalik (0 menjadi 1 atau 1 menjadi 0).mutasi penting agar algoritma tidak terjebak pada solusi lokal dan tetap bisa mengeksplorasi kemungkinan solusi lain.

8.decode(interpretasi solusi)
Fungsi decode() digunakan untuk mengubah representasi biner individu menjadi bentuk yang lebih mudah dipahami,yaitu daftar nama barang yang dipilih beserta total berat dan total nilainya.fungsi ini membantu menampilkan hasil akhir secara jelas kepada pengguna.

9.GA(algoritma utama)
Fungsi GA() menjalankan algoritma genetika.pertama populasi awal dibuat,lalu dalam setiap generasi populasi diurutkan berdasarkan fitness tertinggi ke terendah.nilai fitness terbaik dan rata rata dicatat untuk analisis.beberapa individu terbaik dipertahankan melalui elitisme (ELITE_SIZE).sementara individu lainnya dihasilkan melalui proses seleksi,crossover,dan mutasi hingga populasi baru terbentuk.proses ini diulang selama jumlah generasi yang telah ditentukan.

10.Hasil
setelah proses evolusi selesai (semua generasi dijalankan) program akan memilih solusi terbaik dari populasi terakhir.solusi ini kemudian diterjemahkan menjadi daftar barang yang benar benar dipilih.dan program juga menghitung total berat dan total nilai dari barang tersebut.setelah itu,dilakukan pengecekan apakah total berat masih berada dibawah atau sama dengan kapasitas maksimum.jika masih sesuai,maka solusi dianggap valid,jika tidak maka solusi tidak valid atau tidak digunakan(tetap ditampilkan namun tidak memenuhi syarat).

11.Visualisasi
setelah hasil akhir ketemu,program akan menampilkan grafik menggunakan matplotlib.grafik ini berisi dua garis yaitu nilai terbaik dan nilai rata rata pada setiap generasi.dengan melihat grafik,bisa memahami bagaimana perkembangan kualitas solusi dari awal hingga akhir.biasanya garis akan menunjukkan peningkatan,yang berarti algoritma berhasil menemukan solusi yang semakin baik dari waktu ke waktu.
