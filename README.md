# Membuat-Jadwal-Mata-Kuliah-Dengan-C++
Program ini merupakan implementasi sederhana dalam bahasa C++ untuk mengelola jadwal mata kuliah.
Fitur utama yang tersedia dalam program ini antara lain:

- Menambahkan data mata kuliah (nama, hari, dan jam kuliah).

- Menyimpan jadwal dalam array dengan kapasitas maksimum 10 mata kuliah.

- Menampilkan daftar jadwal mata kuliah yang sudah dimasukkan.

- Menu interaktif agar pengguna dapat memilih aksi yang diinginkan.

[tugasakhir.cpp](https://github.com/user-attachments/files/22580246/tugasakhir.cpp)


``` cpp
#include <iostream>
#include <string>
using namespace std;

struct MataKuliah {
    string nama;
    string hari;
    string jam;
};

int main() {
    const int MAX = 10; // maksimal 10 mata kuliah
    MataKuliah jadwal[MAX];
    int jumlah = 0;
    int pilihan;

    do {
        cout << "\n1. Tambah Mata Kuliah\n2. Tampilkan Jadwal\n0. Keluar\nPilihan: ";
        cin >> pilihan;
        cin.ignore();

        if (pilihan == 1) {
            if (jumlah < MAX) {
                cout << "Nama: ";
                getline(cin, jadwal[jumlah].nama);
                cout << "Hari: ";
                getline(cin, jadwal[jumlah].hari);
                cout << "Jam: ";
                getline(cin, jadwal[jumlah].jam);
                jumlah++;
                cout << "Mata kuliah ditambahkan!\n";
            } else {
                cout << "Jadwal penuh!\n";
            }
        }r
        else if (pilihan == 2) {
            cout << "\n--- Jadwal Mata Kuliah ---\n";
            for (int i = 0; i < jumlah; i++) {
                cout << jadwal[i].nama << " | " 
                     << jadwal[i].hari << " | " 
                     << jadwal[i].jam << endl;
            }
        }
    } while (pilihan != 0);

    return 0;
}
