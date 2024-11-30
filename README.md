# labpy06
Nama : Sayyid Sulthan Abyan <p>
NIM : 312410496 <p>
Kelas : TI.24.A.5 <p>
Mata kuliah : Bahasa Pemrograman <p>
# ```Program Input Nilai```
## Flowchart
![gambar 5](https://github.com/user-attachments/assets/350fe323-30a9-479e-b339-ca25d46ba559)

## Code Program
![gambar 1](https://github.com/user-attachments/assets/5cf5b4a3-6d29-479b-98ec-e0436b605b3b)
![gambar 2](https://github.com/user-attachments/assets/55f2f7c3-f843-4991-8f92-34c54a1907e3)

### Penjelasan Program
1. Header dan Kelas Student:

```python
       print("\nProgram Input Nilai")
       print("===================")
      
       class Student:
           def __init__(self, nim, nama, tugas, uts, uas):
               self.nim = nim
               self.nama = nama
               self.tugas = tugas
               self.uts = uts
               self.uas = uas
               self.akhir = self.calculate_final_grade()
      
           def calculate_final_grade(self):
               return round((self.tugas * 0.3) + (self.uts * 0.35) + (self.uas * 0.35), 2)
   
      - Kode ini mencetak judul program dan mendefinisikan kelas ```Student``` yang memiliki atribut ```nim```, ```nama```, ```tugas```, ```uts```, ```uas```, dan ```akhir```.
      - ```calculate_final_grade``` adalah metode yang menghitung nilai akhir berdasarkan bobot tugas (30%), UTS (35%), dan UAS (35%).
```
       
2. Fungsi Menampilkan Menu dan Daftar Mahasiswa:

```python
       def display_menu():
                     print("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]: ", end=' ')
              
                 def display_students(students):
                     print("\nDaftar Nilai")
                     print("=" * 84)
                     print(f"| {'NO':<3} | {'NIM':<10} | {'NAMA':<30} | {'TUGAS':<6} | {'UTS':<4} | {'UAS':<4} | {'AKHIR':<5} |")
                     print("=" * 84)
                     if not students:
                        print(f"| {'TIDAK ADA DATA':^80} |")
                     else:
                         for i, student in enumerate(students, start=1):
                             print(f"| {i:<3} | {student.nim:<10} | {student.nama:<30} | {student.tugas:<6} | {student.uts:<4} | {student.uas:<4} | {student.akhir:<5} |")
                     print("=" * 84)
          
   - ```display_menu``` menampilkan menu pilihan kepada pengguna.
   - ```display_students``` menampilkan daftar nilai mahasiswa dalam format tabel. Jika tidak ada data, pesan "TIDAK ADA DATA" akan ditampilkan.
```
3. Fungsi Mencari Indeks Mahasiswa:

```python
          def find_student_index(students, nim):
              for index, student in enumerate(students):
                  if student.nim == nim:
                     return index
              return None

   - ```find_student_index``` mencari indeks mahasiswa berdasarkan NIM. Mengembalikan ```None``` jika NIM tidak ditemukan.
```

4. Fungsi Utama:

```python
       def main():
           students = []
           while True:
               display_menu()
               choice = input().lower()
               if choice == 't':
                   nim = input("\nNIM: ")
                   nama = input("Nama: ")
                   tugas = int(input("Nilai Tugas: "))
                   uts = int(input("Nilai UTS: "))
                   uas = int(input("Nilai UAS: "))
                   students.append(Student(nim, nama, tugas, uts, uas))
               elif choice == 'l':
                   display_students(students)
               elif choice == 'u':
                   display_students(students)
                   nim = input("\nMasukkan nama mahasiswa yang akan diubah: ")
                   index = find_student_index(students, nama)
                   if index is not None:
                       print("Data baru:")
                       nama = input("Nama: ")
                       tugas = int(input("Nilai Tugas: "))
                       uts = int(input("Nilai UTS: "))
                       uas = int(input("Nilai UAS: "))
                       students[index] = Student(nim, nama, tugas, uts, uas)
                   else:
                       print("Mahasiswa dengan NIM tersebut tidak ditemukan.")
               elif choice == 'h':
                   display_students(students)
                   nim = input("\nMasukkan nama mahasiswa yang akan dihapus: ")
                   index = find_student_index(students, nama)
                   if index is not None:
                       del students[index]
                       print("Data mahasiswa berhasil dihapus.")
                   else:
                       print("Mahasiswa dengan NIM tersebut tidak ditemukan.")
               elif choice == 'k':
                   break
               else:
                   print("Pilihan tidak valid!")
       
       if __name__ == "__main__":
           main()
```

   - Fungsi ```main``` adalah fungsi utama yang menjalankan program.
   - Variabel ```students``` menyimpan daftar objek ```Student```.
   - Program menampilkan menu dan menangani pilihan pengguna:
     - **Tambah (```t```)**: Menambah data mahasiswa baru ke dalam daftar ```students```.
     - **Lihat (```l```)**: Menampilkan daftar mahasiswa.
     - **Ubah (```u```)**: Mengubah data mahasiswa berdasarkan NIM yang diberikan. Jika NIM ditemukan, data mahasiswa diperbarui dengan data baru.
     - **Hapus (```h```)**: Menghapus data mahasiswa berdasarkan NIM yang diberikan. Jika NIM ditemukan, data mahasiswa dihapus dari daftar students.
     - **Keluar (```k```)**: Keluar dari program.
## Output Program
![gambar 3](https://github.com/user-attachments/assets/d30e93e7-f942-49fa-a790-8ecb1f09fe89)
![gambar 4](https://github.com/user-attachments/assets/4bd1acd7-4ff0-495b-a017-349e0cb24c5f)
