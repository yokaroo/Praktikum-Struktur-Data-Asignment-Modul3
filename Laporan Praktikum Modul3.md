# <h1 align="center">Laporan Praktikum Modul Sorting</h1>
<p align="center">Yoka Romadani</p>
<p align="center">2311110060</p>>
<p align="center">SD04-B</p>

## Dasar Teori
Algoritma Sorting adalah algoritma untuk meletakkan kumpulan elemen data ke dalam urutan 
tertentu, berdasarkan satu atau beberapa kunci ke dalam tiap-tiap elemen 
Berdasarkan data terurutnya, algoritma sorting dibagi menjadi dua jenis, yaitu: 

o Ascending; pengurutan dari terkecil hingga terbesar. Contoh: a, b, c, d, e. 

o Descending; pengurutan dari nilai terbesar hingga terkecil. Contoh: e, d, c, b, a 

## Guided
## 1. Mengurutkan secara ascending untuk data numerik bertipe double menggunakan Algoritma Bubble Sort
```C++
#include <iostream> 
 
using namespace std; 
 
void bubble_sort(double arr[], int length){ 
    bool not_sorted = true; 
    int j=0; 
    double tmp; 
 
    while (not_sorted){ 
        not_sorted = false; 
        j++; 
        for (int i = 0; i < length - j; i++){ 
            if (arr[i] > arr[i + 1]) { 
                tmp = arr[i]; 
		arr[i] = arr[i + 1]; 
                arr[i + 1] = tmp; 
                not_sorted = true; 
            }//end of if 
        }//end of for loop 
  }//end of while loop 
}//end of bubble_sort 
 
void print_array(double a[], int length) { 
 
    for(int i=0; i<length; i++) { 
        cout << a[i] << "\t"; 
    } 
    cout << endl; 
} 
 
int main() { 
 
    int length = 5; 
    double a[] = {22.1, 15.3, 8.2, 33.21, 99,99}; 
 
    cout << "Urutan bilangan sebelum sorting: " << endl; 
    print_array(a, length); 
 
    bubble_sort(a, length); 
 
    cout << "\nUrutan bilangan setelah sorting: " << endl; 
    print_array(a, length); 
}

```
### Output
![Screenshot 2024-06-12 082214](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul2/blob/main/Screenshot%202024-06-12%20082214.png)
## Iterpretasi
Kode program ini mendeklarasikan sebuah array 3 dimensi berukuran 2x3x3 dan meminta pengguna untuk mengisi setiap elemen array melalui input. Program menggunakan tiga loop bersarang untuk mengakses setiap elemen array dan mengisi nilainya. Setelah semua nilai diinput, program menampilkan nilai-nilai tersebut dalam dua format: pertama, dengan menunjukkan indeks setiap elemen dan nilainya, dan kedua, dengan menampilkan elemen-elemen array dalam bentuk baris dan kolom yang lebih mudah dibaca. Program kemudian mengakhiri dengan return 0, menandakan bahwa program selesai dijalankan dengan sukses.

## 2. Program Mencari Nilai Maksimal Pada Aray
```C++
#include <iostream>
using namespace std;

int main() {
    int maks, a, lokasi;
    cout << "Masukkan panjang array: ";
    cin >> a;
    int array[a];

    cout << "Masukkan " << a << " angka\n";
    for (int i = 0; i < a; i++) {
        cout << "Array ke-" << i << ": ";
        cin >> array[i];
    }

    maks = array[0];
    lokasi = 0;  // Inisialisasi lokasi dengan indeks pertama

    for (int i = 1; i < a; i++) {  // Mulai dari indeks ke-1 karena maks sudah diinisialisasi dengan array[0]
        if (array[i] > maks) {
            maks = array[i];
            lokasi = i;
        }
    }

    cout << "Nilai maksimum adalah " << maks << " berada di Array ke-" << lokasi << endl;

    return 0;
}
```
## Output
![Screenshot 2024-06-12 083334](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul2/blob/main/Screenshot%202024-06-12%20083334.png)
## Interpretasi Code
Kode tersebut adalah sebuah program C++ yang mencari nilai maksimum dalam sebuah array yang dimasukkan oleh pengguna. Program ini meminta pengguna untuk memasukkan panjang array dan kemudian mengisi array dengan angka-angka yang diinput oleh pengguna. Setelah array terisi, program mencari nilai maksimum dalam array tersebut dengan memulai perbandingan dari elemen kedua (indeks 1) hingga elemen terakhir. Jika ditemukan nilai yang lebih besar daripada nilai maksimum saat ini, nilai tersebut akan menjadi nilai maksimum yang baru, dan lokasinya (indeks) akan diperbarui. Akhirnya, program menampilkan nilai maksimum dan indeksnya kepada pengguna.

### UnGuided
## 1. Buatlah program untuk menampilkan output seperti berikut dengan data yang ditampilkan user
```C++
//Menggunakan library input/output dan struktur data
#include <iostream>
#include <sstream>
#include <vector>
using namespace std;

//Membuat kode inti atau main code
int main() {
    string name; // membuat variabel
    //membuat vektor bertipe integer
    vector<int> numbers;
    vector<int> evenNumbers;
    vector<int> oddNumbers;
    
    //meminta inputan
    cout << "Masukkan nama Anda:" << endl;
    getline(cin, name);
    cout<<endl;
    //Menyapa pengguna dan meminta inputan angka
    cout<<"Halo, "<< name << ". Selamat datang di Program pemilihan angka genap dan ganjil." << endl<<endl;
    cout << "Masukkan angka anda, pisahkan dengan spasi!" << endl;
    cout << "Klik enter untuk menampilkan hasil !" << endl;
    string input;
    getline(cin, input);
    
    // Membaca angka-angka dari baris input
    stringstream ss(input);
    int num;
    while (ss >> num) {
        numbers.push_back(num);
    }
    
    // Memisahkan angka genap dan ganjil dari inputan pengguna
    for (int num : numbers) {
        if (num % 2 == 0) { //menggunakan modulus
            evenNumbers.push_back(num);  //jika habis di bagi 2 masuk ke sini
        } else {
            oddNumbers.push_back(num); //jika tidak habis masuk kesini
        }
    }
    
    // Menampilkan angka-angka genap
    cout << "Angka genap: ";
    for (int num : evenNumbers) {
        cout << num << " ";
    }
    cout << endl;
    
    // Menampilkan angka-angka ganjil
    cout << "Angka ganjil: ";
    for (int num : oddNumbers) {
        cout << num << " ";
    }
    cout << endl<<endl;
    
    return 0;
}
```
### Output
![Screenshot 2024-06-12 094446](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul2/blob/main/Screenshot%202024-06-12%20094446.png)

## 2. Buatlah program Input array tiga dimensi (seperti pada guided) tetapi jumlah atau ukuran elemennya diinputkan oleh user!
```C++
#include <iostream>
using namespace std;

int main() {
    int x, y, z;

    // Meminta pengguna untuk memasukkan ukuran array
    cout << "Masukkan jumlah baris: ";
    cin >> x;
    cout << "Masukkan jumlah kolom: ";
    cin >> y;
    cout << "Masukkan jumlah depth: ";
    cin >> z;

    // Deklarasi array tiga dimensi
    int arr[x][y][z];

    // Input elemen array
    cout << "Masukkan elemen-elemen array:\n";
    for (int i = 0; i < x; ++i) {
        for (int j = 0; j < y; ++j) {
            for (int k = 0; k < z; ++k) {
                cout << "Array[" << i << "][" << j << "][" << k << "]: ";
                cin >> arr[i][j][k];
            }
        }
    }

    // Output elemen array
    cout << "\nElemen-elemen array yang dimasukkan:\n";
    for (int i = 0; i < x; ++i) {
        for (int j = 0; j < y; ++j) {
            for (int k = 0; k < z; ++k) {
                cout << "Array[" << i << "][" << j << "][" << k << "]: " << arr[i][j][k] << endl;
            }
        }
    }

    return 0;
}

```

## Output
![Screenshot 2024-06-12 094933.png](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul2/blob/main/Screenshot%202024-06-12%20094933.png)

### 3.  Buatlah program menu untuk mencari nilai Maksimum, Minimum dan Nilai rata– rata dari suatu array dengan input yang dimasukan oleh user
```C++
#include <iostream>
#include <climits> // Untuk menggunakan konstanta INT_MIN dan INT_MAX
using namespace std;

int main() {
    int n;

    // Meminta pengguna untuk memasukkan jumlah elemen array
    cout << "Masukkan jumlah elemen array: ";
    cin >> n;

    // Membuat array untuk menyimpan elemen-elemen yang dimasukkan oleh pengguna
    int arr[n];

    // Meminta pengguna untuk memasukkan elemen-elemen array
    cout << "Masukkan elemen-elemen array:\n";
    for (int i = 0; i < n; ++i) {
        cout << "Elemen " << i + 1 << ": ";
        cin >> arr[i];
    }

    // Mencari nilai maksimum, minimum, dan rata-rata
    int maksimum = INT_MIN;
    int minimum = INT_MAX;
    int total = 0;

    for (int i = 0; i < n; ++i) {
        if (arr[i] > maksimum) {
            maksimum = arr[i];
        }
        if (arr[i] < minimum) {
            minimum = arr[i];
        }
        total += arr[i];
    }

    double rata_rata = static_cast<double>(total) / n;

    // Menampilkan hasil
    cout << "\nNilai Maksimum: " << maksimum << endl;
    cout << "Nilai Minimum: " << minimum << endl;
    cout << "Nilai Rata-rata: " << rata_rata << endl;

    return 0;
}
```
## output
![Screenshot 2024-06-12 095423](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul2/blob/main/Screenshot%202024-06-12%20095423.png)

### Kesimpulan 
Dengan pemahaman tentang berbagai jenis array ini, kita dapat lebih efektif menggunakan dan memahami struktur data yang kompleks dan penggunaannya dalam pemrograman. Array merupakan fondasi yang penting dalam mempelajari struktur data lainnya dan memiliki peran yang krusial dalam pengembangan perangkat lunak
