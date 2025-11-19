def tampilkan_detail_hari(jadwal, hari_pilihan):
    """
    Menampilkan detail kegiatan olahraga untuk hari tertentu.
    """
    # Mengubah input menjadi format Title Case (huruf besar di awal) agar sesuai dengan kunci dictionary
    hari_pilihan = hari_pilihan.title()
    
    # Cek apakah hari yang dimasukkan ada dalam jadwal
    if hari_pilihan in jadwal:
        detail = jadwal[hari_pilihan]
        kegiatan = detail['kegiatan']
        waktu = detail['waktu']
        
        print(f"\n✅ *Jadwal Olahraga untuk Hari {hari_pilihan}* ✅")
        print("------------------------------------------")
        print(f"| Kegiatan: *{kegiatan}*")
        print(f"| Waktu:    *{waktu}*")
        print("------------------------------------------")
        
        # Berikan saran tambahan jika ada
        if 'catatan' in detail:
            print(f"*Catatan:* {detail['catatan']}")
    else:
        print(f"\n❌ Maaf, hari '{hari_pilihan}' tidak ditemukan dalam jadwal. Pastikan ejaan sudah benar.")
        print("Hari yang tersedia: " + ", ".join(jadwal.keys()))

# --- Data Jadwal Olahraga (Dictionary) ---
jadwal_olahraga = {
    'Senin': {
        'kegiatan': 'Angkat Beban (Full Body)',
        'waktu': '19:00 - 20:30',
        'catatan': 'Fokus pada compound movements (Squat, Deadlift, Bench).'
    },
    'Selasa': {
        'kegiatan': 'Lari dan Cardio',
        'waktu': '06:30 - 07:30',
        'catatan': 'Lari 5K atau HIIT 30 menit.'
    },
    'Rabu': {
        'kegiatan': 'Istirahat Aktif (Yoga/Stretching)',
        'waktu': '17:00 - 17:45',
        'catatan': 'Penting untuk pemulihan otot (muscle recovery).'
    },
    'Kamis': {
        'kegiatan': 'Berenang',
        'waktu': '18:30 - 19:30',
        'catatan': 'Fokus pada teknik pernapasan dan endurance.'
    },
    'Jumat': {
        'kegiatan': 'Olahraga Tim (Futsal/Basket)',
        'waktu': '20:00 - 21:30',
        'catatan': 'Meningkatkan kelincahan dan kerja sama tim.'
    },
    'Sabtu': {
        'kegiatan': 'Hiking/Sepeda Jarak Jauh',
        'waktu': '08:00 - 11:00',
        'catatan': 'Kegiatan outdoor untuk variasi dan kesehatan mental.'
    },
    'Minggu': {
        'kegiatan': 'Istirahat Total',
        'waktu': '-',
        'catatan': 'Pastikan tidur cukup dan nutrisi terpenuhi.'
    }
}

# --- Bagian Utama Program (Main Execution) ---

print("Selamat datang di Pencari Jadwal Olahraga Harian!")

# Minta input dari pengguna
hari = input("Masukkan hari yang ingin Anda cek (contoh: Senin, Minggu): ")

# Panggil fungsi untuk menampilkan hasilnya
tampilkan_detail_hari(jadwal_olahraga, hari)
