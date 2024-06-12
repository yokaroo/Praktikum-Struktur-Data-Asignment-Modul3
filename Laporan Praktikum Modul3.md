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
![Screenshot 2024-06-12 205417](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul3/blob/main/Screenshot%202024-06-12%20205417.png)
## Iterpretasi
Program C++ ini menggunakan algoritma Bubble Sort untuk mengurutkan sebuah array `double`. Fungsi `bubble_sort` mengurutkan elemen array secara menaik dengan membandingkan elemen-elemen berdekatan dan menukarnya jika elemen pertama lebih besar dari elemen kedua. Fungsi `print_array` mencetak elemen-elemen array ke konsol. Dalam `main`, sebuah array `a` dideklarasikan dengan lima elemen. Program mencetak array sebelum dan sesudah pengurutan menggunakan Bubble Sort. Elemen array diurutkan dan ditampilkan dalam urutan yang benar.

## 2. Mengurutkan karakter secara descending (dari terbesar hingga terkecil) menggunakan Algoritma Insertion Sort
```C++
#include <iostream> 
 
using namespace std; 
 
void insertion_sort(char arr[], int length) { 
    int i, j; 
    char tmp; 
 
    for (i = 1; i < length; i++) { 
     j = i; 
 
        while (j > 0 && arr[j - 1] < arr[j]) { 
            tmp = arr[j]; 
            arr[j] = arr[j - 1]; 
            arr[j - 1] = tmp; 
            j--; 
        }//end of while loop 
    }//end of for loop 
} 
 
void print_array(char a[], int length) { 
 
    for(int i=0; i<length; i++) { 
        cout << a[i] << "\t"; 
    } 
    cout << endl; 
}
int main() { 
	int length = 6; 
	char a[length] = {'c', 'f', 'a', 'z', 'd', 'p'}; 
	cout << "Urutan karakter sebelum sorting: " << endl; 
	print_array(a, length); 
	insertion_sort(a, length); 
	cout << "\nUrutan karakter setelah sorting: " << endl; 
	print_array(a, length); 
} 
```
## Output
![Screenshot 2024-06-12 210111](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul3/blob/main/Screenshot%202024-06-12%20210111.png)
## Interpretasi Code
Program C++ ini menggunakan algoritma Insertion Sort untuk mengurutkan sebuah array dari karakter. Fungsi `insertion_sort` menerima array dan panjangnya sebagai parameter, lalu mengurutkan elemen array secara menurun. Algoritma ini bekerja dengan membandingkan setiap elemen dengan elemen-elemen sebelumnya, dan menukar posisinya jika diperlukan untuk memastikan bahwa elemen-elemen tersebut berada dalam urutan yang benar. Fungsi `print_array` digunakan untuk mencetak elemen-elemen array ke konsol, dipisahkan oleh tab. Dalam `main`, sebuah array `a` dideklarasikan dengan enam karakter. Program mencetak array sebelum dan sesudah pengurutan menggunakan Insertion Sort, sehingga kita dapat melihat perubahan urutan karakter dari tidak terurut menjadi terurut secara menurun.

### UnGuided
## 1. Kelas S1 IF 2016 G memiliki 5 mahasiswa. Pada akhir semester mereka menerima lembar Indeks Prestasi Semester (IPS), masing-masing mahasiswa tersebut memiliki IPS sebagai berikut: {3.8, 2.9, 3.3, 4.0, 2.4}. Buatlah program untuk mengurutkan IPS mahasiswa tersebut dari yang terbesar hingga terkecil dengan menggunakan algoritma Selection Sort!  (Score: 30)
```C++
#include <iostream>

using namespace std;

// Fungsi untuk mengurutkan array menggunakan Selection Sort
void selectionSortDescending(float arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        // Mencari elemen terbesar di subarray yang tidak diurutkan
        int maxIdx = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] > arr[maxIdx]) {
                maxIdx = j;
            }
        }
        
        // Menukar elemen terbesar dengan elemen pertama di subarray yang tidak diurutkan
        float temp = arr[maxIdx];
        arr[maxIdx] = arr[i];
        arr[i] = temp;
    }
}

// Fungsi untuk mencetak array
void printArray(float arr[], int size) {
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main() {
    // Array IPS mahasiswa
    float ips[] = {3.8, 2.9, 3.3, 4.0, 2.4};
    int n = sizeof(ips) / sizeof(ips[0]);
    
    // Mengurutkan array
    selectionSortDescending(ips, n);
    
    // Mencetak hasil pengurutan
    cout << "IPS mahasiswa dari yang terbesar hingga terkecil: ";
    printArray(ips, n);
    
    return 0;
}

```
### Output
![Screenshot 2024-06-12 210538](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul3/blob/main/Screenshot%202024-06-12%20210538.png)

## 2. Pak RT memiliki 10 warga dengan nama: siti, situ, sana, ana, ani, caca, cici, dida, dodo, dan dadi. Supaya mudah dalam melakukan pencarian, Pak RT akan mengurutkan namanama tersebut sesuai dengan alfabet. Buatlah program untuk membantu Pak RT dengan menggunakan algoritma Bubble Sort! (Score: 30) 
```C++
#include <iostream>
#include <string>

using namespace std;

// Fungsi untuk mengurutkan array menggunakan Bubble Sort
void bubbleSort(string arr[], int n) {
    bool swapped;
    for (int i = 0; i < n - 1; i++) {
        swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Menukar elemen jika urutan salah
                string temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                swapped = true;
            }
        }
        // Jika tidak ada elemen yang ditukar, maka array sudah terurut
        if (!swapped)
            break;
    }
}

// Fungsi untuk mencetak array
void printArray(string arr[], int size) {
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main() {
    // Array nama warga
    string warga[] = {"siti", "situ", "sana", "ana", "ani", "caca", "cici", "dida", "dodo", "dadi"};
    int n = sizeof(warga) / sizeof(warga[0]);
    
    // Mengurutkan array
    bubbleSort(warga, n);
    
    // Mencetak hasil pengurutan
    cout << "Nama warga yang sudah diurutkan sesuai alfabet: ";
    printArray(warga, n);
    
    return 0;
}
```

## Output
![Screenshot 2024-06-12 211028](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul3/blob/main/Screenshot%202024-06-12%20211028.png)

### 3.   Buatlah program yang meminta user menginputkan suatu bilangan n dan meminta user untuk menginputkan sejumlah n karakter. Kemudian program akan melakukan sorting secara menaik (ascending) dan menurun (descending)! (Score: 40)
```C++
#include <iostream>
#include <vector>
#include <algorithm> // Untuk std::swap

using namespace std;

// Fungsi untuk mengurutkan array menggunakan Bubble Sort (ascending)
void bubbleSortAscending(vector<char>& arr) {
    int n = arr.size();
    bool swapped;
    for (int i = 0; i < n - 1; i++) {
        swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        if (!swapped)
            break;
    }
}

// Fungsi untuk mengurutkan array menggunakan Bubble Sort (descending)
void bubbleSortDescending(vector<char>& arr) {
    int n = arr.size();
    bool swapped;
    for (int i = 0; i < n - 1; i++) {
        swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] < arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        if (!swapped)
            break;
    }
}

// Fungsi untuk mencetak array
void printArray(const vector<char>& arr) {
    for (char c : arr) {
        cout << c << endl;
    }
}

int main() {
    int n;
    cout << "input (n) = ";
    cin >> n;

    vector<char> characters(n);

    for (int i = 0; i < n; i++) {
        cout << "Karakter ke-" << i + 1 << ": ";
        cin >> characters[i];
    }

    cout << "\nUrutan karakter sebelum sorting:" << endl;
    printArray(characters);

    // Mengurutkan secara ascending
    bubbleSortAscending(characters);
    cout << "\nUrutan karakter setelah ascending sort:" << endl;
    printArray(characters);

    // Mengurutkan secara descending
    bubbleSortDescending(characters);
    cout << "\nUrutan karakter setelah descending sort:" << endl;
    printArray(characters);

    return 0;
}


```
## output
![Screenshot 2024-06-12 212302](https://github.com/yokaroo/Praktikum-Struktur-Data-Asignment-Modul3/blob/main/Screenshot%202024-06-12%20212302.png)

### Kesimpulan 
Kedua program menggunakan algoritma pengurutan yang berbeda, yaitu Bubble Sort dan Insertion Sort, untuk mengurutkan array. Mereka berfungsi dengan cara yang sama, yaitu dengan membandingkan elemen-elemen array dan menukar posisi mereka jika diperlukan. Hasilnya adalah array yang diurutkan sesuai dengan aturan pengurutan yang ditentukan.
