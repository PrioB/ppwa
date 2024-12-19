---
title: 210411100177_Prio Budi Laksono_Eksplorasi Mandiri SKIP GRAM

---

## Tugas Eksplorasi Mandiri Skip Gram
#### Nama : Prio Budi Laksono
#### NIM  : 210411100177
#### Kelas : Pencarian dan Penambangan Web
#### SKIP GRAM
Skip-gram adalah teknik dalam pemrosesan bahasa yang mencoba memprediksi kata-kata di sekitar sebuah kata target. Misalnya, jika ada kalimat "Saya suka makan roti", dan kata targetnya "suka", skip-gram akan berusaha menebak kata-kata yang muncul di sekitarnya, seperti "Saya" dan "makan". Tujuannya adalah untuk melatih model agar memahami hubungan antar kata dalam kalimat.

Contoh penggunaan skip gram :+1: 

Sebagai contoh kalimat "The man who passes the should swing the sword".
| Kata Target | Kata Konteks         |
|-------------|----------------------|
| The         | man                  |
| man         | The, who             |
| who         | man, passes          |
| passes      | who, the             |
| the         | passes, should       |
| should      | the, swing           |
| swing       | should, the          |
| the         | swing, sword         |
| sword       | the                  |

Iterasi Pertama :
| Kata                | the | man | who | passes | the | should | swing | the | sword |
|---------------------|---|---|---|---|---|---|---|---|---|
| the                 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| man                 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| who                 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| passes              | 0 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 |
| the                 | 0 | 0 | 0 | 1 | 0 | 1 | 0 | 0 | 0 |
| should              | 0 | 0 | 0 | 0 | 1 | 0 | 1 | 0 | 0 |
| swing               | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 | 0 |
| the                 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 |
| sword               | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 |

Iterasi Kedua : 
| Kata     | the | man | who | passes | the | should | swing | the | sword |
|----------|-----|-----|-----|--------|-----|--------|-------|-----|-------|
| the      | 0   | 2   | 1   | 1      | 0   | 0      | 0     | 0   | 0     |
| man      | 2   | 0   | 2   | 1      | 0   | 0      | 0     | 0   | 0     |
| who      | 1   | 2   | 0   | 2      | 1   | 0      | 0     | 0   | 0     |
| passes   | 0   | 1   | 2   | 0      | 2   | 1      | 0     | 0   | 0     |
| the      | 0   | 0   | 1   | 2      | 0   | 2      | 1     | 0   | 0     |
| should   | 0   | 0   | 0   | 1      | 2   | 0      | 2     | 1   | 0     |
| swing    | 0   | 0   | 0   | 0      | 1   | 2      | 0     | 2   | 1     |
| the      | 0   | 0   | 0   | 0      | 0   | 1      | 2     | 0   | 2     |
| sword    | 0   | 0   | 0   | 0      | 0   | 0      | 1     | 2   | 0     |

#### Kesimpulan Perhitungan Co-Occurrence

#### Iterasi 1
Pada iterasi pertama, perhitungan co-occurrence hanya dilakukan dalam jendela konteks yang sangat dekat, yaitu dengan menghitung kemunculan kata-kata yang langsung bersebelahan. Dalam pendekatan ini, setiap kata hanya mempertimbangkan kata yang berada di sebelah kiri dan kanan secara langsung.

#### Iterasi 2
Pada iterasi kedua, pendekatan yang lebih luas diterapkan dengan menghitung kemunculan bersama dari kata-kata yang sedikit lebih jauh dalam kalimat. Dengan memperluas jendela konteks, beberapa nilai co-occurrence bertambah, mencerminkan hubungan yang lebih kompleks antara kata-kata dalam kalimat tersebut.

Melalui dua iterasi ini, kita dapat melihat bagaimana ukuran jendela konteks memengaruhi hasil perhitungan co-occurrence dan memberikan wawasan yang lebih dalam mengenai keterkaitan antara kata-kata.

#### WORD EMBEDDING
Word embedding adalah cara mengubah kata-kata menjadi angka (vektor) sehingga komputer bisa memahami dan bekerja dengan kata-kata. Vektor ini menggambarkan arti kata, jadi kata-kata yang mirip akan memiliki angka-angka yang mirip. Misalnya, kata "raja" dan "ratu" akan memiliki representasi angka yang dekat karena maknanya terkait.

#### CBOW
CBOW (Continuous Bag of Words) adalah teknik dalam pemrosesan bahasa yang memprediksi kata target berdasarkan kata-kata di sekitarnya. Misalnya, jika ada kalimat "Saya suka makan roti", CBOW akan menggunakan kata-kata "Saya", "makan", dan "roti" untuk memprediksi kata target "suka". Tujuannya adalah melatih model agar memahami konteks di mana kata muncul.

CBOW adalah kebalikan dari skip-gram, yang memprediksi kata konteks dari kata target.