```
package com.spbu.entity;

/**
 *
 * @author nuNox
 */
public class SPBU {
    private String id;
    private String nama;
    private String alamat;

    public SPBU(String id, String nama, String alamat) {
        this.id = id;
        this.nama = nama;
        this.alamat = alamat;
    }

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getNama() {
        return nama;
    }

    public void setNama(String nama) {
        this.nama = nama;
    }

    public String getAlamat() {
        return alamat;
    }

    public void setAlamat(String alamat) {
        this.alamat = alamat;
    }

    public void displayInfo() {
        System.out.println("ID: " + id);
        System.out.println("Nama: " + nama);
        System.out.println("Alamat: " + alamat);
    }
}
```
Paket 1: com.spbu.entity

SPBU.java
Kelas ini mewakili entitas SPBU tunggal. Kelas ini memiliki tiga properti:

id: identifikasi unik untuk SPBU

nama: nama SPBU

alamat: alamat SPBU

Kelas ini memiliki konstruktor yang mengambil id, nama, dan alamat sebagai parameter serta kelas ini juga memiliki metode getter dan setter untuk setiap properti.

Metode displayInfo() digunakan untuk menampilkan informasi SPBU.
```
package com.spbu.entity;

/**
 *
 * @author nuNox
 */
import java.util.ArrayList;
import java.util.List;

public class Pengelola {
    private String id;
    private String nama;
    private List<SPBU> daftarSPBU;

    public Pengelola(String id, String nama) {
        this.id = id;
        this.nama = nama;
        this.daftarSPBU = new ArrayList<>();
    }

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getNama() {
        return nama;
    }

    public void setNama(String nama) {
        this.nama = nama;
    }

    public List<SPBU> getDaftarSPBU() {
        return daftarSPBU;
    }

    public void setDaftarSPBU(List<SPBU> daftarSPBU) {
        this.daftarSPBU = daftarSPBU;
    }

    public void tambahSPBU(SPBU spbu) {
        daftarSPBU.add(spbu);
    }

    public void hapusSPBU(SPBU spbu) {
        daftarSPBU.remove(spbu);
    }

    public void displayDaftarSPBU() {
        for (SPBU spbu : daftarSPBU) {
            spbu.displayInfo();
        }
    }
}
```
Pengelola.java
Kelas ini mewakili pengelola entitas SPBU. Kelas ini memiliki tiga properti:

id: identifikasi unik untuk pengelola

nama: nama pengelola

daftarSPBU: daftar entitas SPBU yang dikelola oleh pengelola

Kelas ini memiliki konstruktor yang mengambil id dan nama sebagai parameter serta kelas ini juga memiliki metode getter dan setter untuk setiap properti.

Metode tambahSPBU(SPBU spbu) digunakan untuk menambahkan SPBU baru ke daftar SPBU yang dikelola, Metode hapusSPBU(SPBU spbu) digunakan untuk menghapus SPBU dari daftar SPBU yang dikelola, dan Metode displayDaftarSPBU() digunakan untuk menampilkan daftar SPBU yang dikelola.
```
package com.spbu.main;

/**
 *
 * @author nuNox
 */
import com.spbu.entity.Pengelola;
import com.spbu.entity.SPBU;

public class Main {
    public static void main(String[] args) {
        Pengelola pengelola = new Pengelola("1", "Pengelola SPBU");

        SPBU spbu1 = new SPBU("1", "SPBU SHELL DELTAMAS-1 BKS", "JALAN BOULEVARD DELTA MAS\n" +
"BEKASI, Jawa Barat West Java, 17530");
        SPBU spbu2 = new SPBU("2", "SHELL LIPPO CIKARANG-1 BKS", "KECAMATAN CIKARANG SELATAN\n" +
"BEKASI, Jawa Barat West Java, 17550");

        pengelola.tambahSPBU(spbu1);
        pengelola.tambahSPBU(spbu2);

        System.out.println("Daftar SPBU:");
        pengelola.displayDaftarSPBU();

        pengelola.hapusSPBU(spbu1);

        System.out.println("Daftar SPBU setelah dihapus:");
        pengelola.displayDaftarSPBU();
    }
}
```
Paket 2: com.spbu.main

Main.java
Kelas ini adalah titik masuk program, memiliki metode main() yang membuat instance baru dari kelas Pengelola dan menambahkan dua entitas SPBU baru ke daftar SPBU yang dikelola. Kemudian, program menampilkan daftar SPBU yang dikelola, menghapus salah satu entitas SPBU, dan menampilkan daftar SPBU yang dikelola yang telah diperbarui.

Alur Program

Program dimulai dengan membuat instance baru dari kelas Pengelola dengan id dan nama.
Dua entitas SPBU baru dibuat dan ditambahkan ke daftar SPBU yang dikelola menggunakan metode tambahSPBU(SPBU spbu).
Program menampilkan daftar SPBU yang dikelola menggunakan metode displayDaftarSPBU().
Salah satu entitas SPBU dihapus dari daftar SPBU yang dikelola menggunakan metode hapusSPBU(SPBU spbu).
Program menampilkan daftar SPBU yang dikelola yang telah diperbarui menggunakan metode displayDaftarSPBU().
