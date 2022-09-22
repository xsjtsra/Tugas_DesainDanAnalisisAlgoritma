### Nama : Fatimah Azzahra Maulida

### NIM : 2110131220020

`Desain dan Analisis Algoritma - Pendidikan Ilmu Komputer FKIP`

---

# <p align=center>Rangkuman Materi Tentang Time Complexity dan Big-O Notation</P>

Kompleksitas suatu algoritma dibagi menjadi 2, yaitu Time Complexity dan Space Complexity.

<p align=justify>Time Complexity adalah seberapa lama waktu yang diperlukan untuk menjalankan suatu algoritma. Sedangkan Space Complexity adalah seberapa besar memori yang kita gunakan untuk menjalankan suatu algoritma. Dan disini kita hanya akan membahas tentang Time Complexity.</p>

### **Algoritma**

<p align=justify>Sebelum kita melanjutkan pembahasan, kita harus mengerti dulu apa itu algoritma. Algoritma adalah serangkaian proses yang dilakukan secara berurutan untuk menyelesaikan sebuah permasalahan. Algoritma bisa bermacam-macam tergantung kepada siapa yang membuat algoritma tersebut.</p>

### **Big-O notation**

<p align=justify><b>Time Complexity Analysis</b> adalah suatu cara sederhana untuk mengetahui berapa lama waktu yang dibutuhkan untuk menjalankan suatu algoritma dengan input tertentu (n). Biasanya lebih dikenal dengan sebutan <b>Big-O Notation</b>.</p>

<p align=justify>Big-O Notation adalah cara untuk mengkonversi keseluruhan langkah-langkah suatu algoritma kedalam bentuk Aljabar, yaitu dengan menghiraukan konstanta yang lebih kecil dan koefisien yang tidak berdampak besar terhadap keseluruhan kompleksitas permasalahan yang diselesaikan oleh algoritma tersebut.</p>

Mari kita liat contoh dibawah ini:

    Regular       Big-O
    2             O(1)   --> It's just a constant number
    2n + 10       O(n)   --> n has the largest effect
    5n^2          O(n^2) --> n^2 has the largest effect

<p align=justify>Sederhananya, semua contoh yang ada diatas mengatakan bahwa <i>“kita hanya akan melihat faktor yang memiliki dampak paling besar terhadap nilai yang dihasilkan oleh algoritma tersebut”</i>.</p>

Terdapat beberapa macam time complexity, diantaranya:

### **O(1) — Constant Time**

<p align=justify><b>Constant Time</b> artinya banyaknya input yang diberikan kepada sebuah algoritma, tidak akan mempengaruhi waktu proses (runtime) dari algoritma tersebut.</p>
  
Mari kita liat contoh dibawah ini:

    let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
    function getFirst(input){
      return input[0]; // selalu melakukan 1 langkah
    }
    let firstEl = getFirst(myArray);
  
<p align=justify>Contoh diatas, terdapat sebuah fungsi untuk mengambil elemen pertama dari sebuah input array. Kita bisa melihat bahwa berapapun jumlah array yang diberikan kepada fungsi tersebut, dia akan selalu melakukan 1 hal, yaitu mengambil elemen pertama. Itu artinya <b>jumlah input yang diberikan tidak mempengaruhi waktu proses (<i>runtime</i>) dari algoritma tersebut</b>.</p>
  
<p align=center><img src="https://user-images.githubusercontent.com/112606990/191747764-420fb634-8a5c-4bac-ad68-250e295ff428.png" width=500 heigth=300></p>
  
##### <p align=center>Constain Time</p>
  
### **O(log n) — Logarithmic Time**
  
<p align=justify><b>Logarithmic Time</b> artinya ketika kita memberikan input sebesar n terhadap sebuah fungsi, jumlah tahapan yang dilakukan oleh fungsi tersebut berkurang berdasarkan suatu faktor. Salah satu contohnya adalah algoritma <b>Binary Search</b>.</p>
  
<p align=justify><b>Binary Search</b> adalah algoritma yang kita gunakan dalam mencari posisi nilai dari suatu array dengan cara ‘mengeliminasi’ setengah dari array input untuk mempercepat proses pencarian.</p>
  
Mari kita liat contoh dibawah ini:

    let sortedArray = [11, 24, 30, 43, 51, 61, 73, 86];
    function isExists(number, array){
        var midPoint = Math.floor( array.length /2 );
        if( array[midPoint] === num) return true;
        let isFirstHalf = false;
        if( array[midPoint] < num ) isFirstHalf = true;
  
        else if( array[midpoint] > num ) isFirstHalf = false;
        if (array.length == 1) return false;
        else { 
            // memanggil fungsi yang sama dengan mengeleminiasi setengah dari input array

            if (isFirstHalf) 
                return isExists(number, getFirstHalf(array));
            else 
                return isExists(number, getSecondHalf(array));
        }
    }
    isExists (24, sortedArray); // return true
    isExists (27, sortedArray); // return false
  
### **O(n) — Linear Time**
  
  <p align=justify><b>Linear Time</b> adalah ketika <i>runtime</i> dari fungsi kita berbanding lurus dengan jumlah input yang diberikan.</p>
  
Mari kita liat contoh dibawah ini:
  
    let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
     function getMax(input){
        var max = 0;
        for (var i=0; i<input.length; i++){
            if (max < input[i])
                max = input[i];
        }
        return max;
    }
    let maxNumber = getMax(myArray);
  
<p align=justify>Kita bisa melihat bahwa <b>semakin banyak jumlah input yang diberikan, maka waktu proses/runtime dari fungsi tersebut akan semakin besar</b>.</p>
  
<p align=center><img src="https://user-images.githubusercontent.com/112606990/191747761-21337d64-5325-43bd-8692-e769e72c801d.png" width=500 heigth=300></p>
  
##### <p align=center>Linear Time</p>
  
### **O(n²) — Quadratic Time**
  
<p align=justify><b>Quadratic Time</b> adalah ketika runtime dari fungsi kita adalah sebesar n^2, dimana n adalah jumlah input dari fungsi tersebut. Hal tersebut bisa terjadi karena kita menjalankan <b>fungsi linear didalam fungsi linear</b> (n*n).</p>
  
Mari kita liat contoh dibawah ini:
  
    let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
    function sort(input){
        var sortedArray = [];
        for (var i=0; i<input.length; i++){ // O(n)
            let min = input[i];
            for (var j=i+1; i<input.length; i++){ // O(n)
                if (input[i] < input[j])
                    min = input[j];
            }
            sortedArray.push(min);

       }
        return sortedArray;
    }
    let sortedArray = sort(myArray);
                                        
<p align=center><img src="https://user-images.githubusercontent.com/112606990/191747768-125eb9aa-71e4-42a1-8c00-93a071a5ac74.png" width=500 heigth=300></p>
  
##### <p align=center>Quadratic Time</p>
  
### **O(2^n) — Exponential Time**
  
<p align=justify><b>Exponential Time</b> biasanya digunakan dalam situasi dimana kita tidak terlalu tahu terhadap permasalahan yang dihadapi, sehingga mengharuskan kita mencoba setiap <b>kombinasi</b> dan <b>permutasi</b> dari semua kemungkinan.</p>
  
<p align=center><img src="https://user-images.githubusercontent.com/112606990/191747749-34c1fe26-e8bf-4e8e-a526-004929baa07a.png" width=500 heigth=300></p>
  
##### <p align=center>Exponential Time</p>
