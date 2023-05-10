# kedai_kopi_aknas
class Diskon:
    def __init__(self, jumlah_pesanan, harga):
        self.jumlah_pesanan = jumlah_pesanan
        self.harga = harga
        self.ppn = int(harga * 0.1)
        self.diskon = self.hitung_diskon()
        self.total_harga = self.hitung_total_harga()

    def hitung_diskon(self):
        if self.jumlah_pesanan >= 5:
            if self.harga >= 100000:
                return int(self.harga * 0.3)
            elif self.harga >= 75000:
                return int(self.harga * 0.25)
            elif self.harga >= 50000:
                return int(self.harga * 0.2)
            elif self.harga >= 25000:
                return int(self.harga * 0.15)
            else:
                return int(self.harga * 0.1)
        else:
            return 0

    def hitung_total_harga(self):
        return int(self.harga - self.diskon + self.ppn)

pilihan="y"
while pilihan=="y":
    print("""
    ==============================
    
    Ananda Coffe
    List Menu Minuman Kopi
 
    ==============================
    A. ES Kopi Susu : Rp 11.000
    B. ES Kopi Coklat : Rp 12.000
    C. ES Kopi Hitam : Rp 11.000
    D. Ice Americano : Rp 14.000
    ==============================
    """)
    pesan=str(input("masukkan list abjad menu kopi ="))
    jumlahpesan=int(input("masukkan jumlah pesanan ="))
    if pesan == "a":
        listnama= "ES Kopi Susu"
        harga=(11000*jumlahpesan)
        diskon_obj = Diskon(jumlahpesan, harga)
    elif pesan == "b":
        listnama= "ES Kopi Coklat"
        harga = (12000*jumlahpesan)
        diskon_obj = Diskon(jumlahpesan, harga)
    elif pesan == "c":
        listnama= "ES Kopi Hitam"
        harga=int(11000*jumlahpesan)
        diskon_obj = Diskon(jumlahpesan, harga)
    elif pesan == "d":
        listnama= "ES Americano"
        harga=int(14000*jumlahpesan)
        diskon_obj = Diskon(jumlahpesan, harga)
    else:
        listnama = "-"
        harga = "-"
        ppn = "-"
        diskon = "-"
        totalharga = "-"
        pilihan=input("menu tidak tersedia, silahkan masukkan abjad menu yang tersedia silahkan ulangi kembali Y/N =")
        continue
 
    print("--------------------------")
    print("Ananda Coffe")
    print("--------------------------")
    print("Menu :",listnama)
    print("Jumlah Pesan :", jumlahpesan)
    print("Harga :", harga)
    print("Diskon :", diskon_obj.diskon)
    print("PPN :", diskon_obj.ppn)
    print("--------------------------")
    print("Jumlah Bayar :", diskon_obj.total_harga)
    print("--------------------------")
    pilihan=input("apakah anda ingin order kembali Y/N =")
