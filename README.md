# Membuat-Jadwal-Mata-Kuliah-Dengan-C-
Berikut adalah source code untuk membuat jadwal mata kuliah dengan menambahkan mata kuliah dan menampilkannya menggunakan array pada bahasa c++

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
