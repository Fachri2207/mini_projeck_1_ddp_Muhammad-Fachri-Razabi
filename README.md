# mini_projeck_1_ddp_Muhammad-Fachri-Razabi
nama : Muhammad fachri Razabi
kelas : B 
NIM : 069

while True:
    print("=== MENU MUATAN CPO ===")
    print("1. Tambah Data")
    print("2. Tampilkan Data")
    print("3. Hapus Data")
    print("4. Keluar")
    pilihan = input("Pilih menu (1-4): ")

    if pilihan == "1":
        nama = input("Nama Kapal   : ")
        tujuan = input("Tujuan       : ")
        jumlah = input("Jumlah (ton) : ")

        if nama == "" or tujuan == "" or not jumlah.isdigit():
            print("Gagal! Data tidak valid (nama/tujuan kosong atau jumlah bukan angka).")
        else:
            data_muatan.append((nama, tujuan, jumlah))
            print("Data berhasil ditambahkan.")

    elif pilihan == "2":
        if len(data_muatan) == 0:
            print("Belum ada data muatan.")
        else:
            print("No | Nama Kapal | Tujuan | Jumlah (ton)")
            for i in range(len(data_muatan)):
                nama, tujuan, jumlah = data_muatan[i]
                print(str(i + 1) + ". " + nama + " | " + tujuan + " | " + jumlah)

    elif pilihan == "3":
        if len(data_muatan) == 0:
            print("Belum ada data yang bisa dihapus.")
        else:
            print("No | Nama Kapal | Tujuan | Jumlah (ton)")
            for i in range(len(data_muatan)):
                nama, tujuan, jumlah = data_muatan[i]
                print(str(i + 1) + ". " + nama + " | " + tujuan + " | " + jumlah)

            no = input("Nomor data yang dihapus: ")

            if not no.isdigit() or int(no) < 1 or int(no) > len(data_muatan):
                print("Nomor tidak valid.")
            else:
                dihapus = data_muatan.pop(int(no) - 1)
                print("Data " + dihapus[0] + " berhasil dihapus.")

    elif pilihan == "4":
        print("Terima kasih telah menggunakan program ini.")
        break

    else:
        print("Pilihan tidak valid, coba lagi.")
