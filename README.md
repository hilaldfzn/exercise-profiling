# **Exercise Profiling**
**Muhammad Hilal Darul Fauzan**<br/>
**2206830542**<br/>
**Pemrograman Lanjut C**<br/>

## **Tutorial Modul 5: Java Profiling**

### JMeter Report and Test Results
Hasil JMeter GUI sebelum *profiling*:<br>
![/all-studentendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217445204919980152/image.png?ex=66040d33&is=65f19833&hm=76deaed13d21d437dea9e81b74cc926e946eb62efd802cc8da4e9cfdb63d4199&)
![/all-student-nameendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217445833524646038/image.png?ex=66040dc9&is=65f198c9&hm=fe864dafed65d260acad957bb73331835827afdbd8a4ecb30636efc3a7d8188d&)
![/highest-gpaendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217446123132948580/image.png?ex=66040e0e&is=65f1990e&hm=746e9ccefcb9dcda8a4e0354f126290345f6718e216f063429bd32e35679bdf3&)

Hasil JMeter CLI sebelum *profiling*:<br>
![/all-studentendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217450147634614312/image.png?ex=660411ce&is=65f19cce&hm=c72afc023d645c39419c259cb5971136ef2a2e66d8c126642917a07e8bc771c3&)
![/all-student-nameendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217450217100546139/image.png?ex=660411de&is=65f19cde&hm=d273790610c0410b62e618e66dd2f8bf128d8994a0f64e4ddda80828adb5ad1a&)
![/highest-gpaendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217450286373666948/image.png?ex=660411ef&is=65f19cef&hm=f909287b4423f614a98c7b9b36c595d58938885412453b7a8240c9532d446260&)

Hasil JMeter GUI setelah *profiling*:<br>
![/all-studentendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217461881229541416/image.png?ex=66041cbb&is=65f1a7bb&hm=a7cf4c1506b604cd97def81fb0e36c60c50d8f9297c13fe7f60722ff008ed0ef&)
![/all-student-nameendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217462019364749332/image.png?ex=66041cdc&is=65f1a7dc&hm=dd79f5690133082d613ceecac5a7dc9dba432bed4bb04ee308fce90f7077c4f7&)
![/highest-gpaendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217462389067481148/image.png?ex=66041d34&is=65f1a834&hm=3da8f50dfd9b659d985d106c358446a200c0d50b6bd3c822e831fdf509cfe371&)

Hasil JMeter CLI setelah *profiling*:<br>
![/all-studentendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217463185787846656/image.png?ex=66041df2&is=65f1a8f2&hm=6ee38b163c8082ad64b673b420a3ff7e9c91faed576a5d32bf73d2fb60794941&)
![/all-student-nameendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217463277618204682/image.png?ex=66041e08&is=65f1a908&hm=89473d3642ad197225b2175a53c427d74676f3d302b6c40e92dcc5b936014a81&)
![/highest-gpaendpoint](https://cdn.discordapp.com/attachments/1208439913247412335/1217463346199134270/image.png?ex=66041e19&is=65f1a919&hm=b5c94619f49af7ee953020d6f776ad4ecdcb4fae10f28a17f3f4c636622cdf6c&)

Berdasarkan gambar di atas, terlihat ada peningkatan performa yang dapat dilihat dari *sample time* yang didapat. Waktu eksekusi sebelum dilakukan optimisasi tercatat lebih panjang dibandingkan setelah proses optimisasi. Kesimpulan yang bisa diambil adalah bahwa upaya optimisasi yang saya lakukan dengan menggunakan alat seperti JMeter dan Intellij Profiler terbukti berhasil.

### Reflection

1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?

    Menggunakan JMeter dalam pengujian biasanya tidak menggali aspek internal dari sebuah aplikasi atau program, menjadikannya lebih mirip dengan teknik pengujian blackbox. Alat ini prinsipnya mengirimkan permintaan ke endpoint tertentu, berdasarkan volume yang diatur oleh pengguna, dan kemudian menilai kemampuan sistem untuk memproses permintaan tersebut dan memberikan respons. Sebaliknya, teknik profiling memungkinkan pemeriksaan yang lebih detail terhadap apa yang terjadi di dalam program ketika menerima permintaan. Dengan teknik ini, saya bisa menentukan komponen mana dalam program yang memakan waktu eksekusi terpanjang dibandingkan komponen lain, sehingga memfasilitasi optimisasi kode yang lebih tertarget dan efisien.

2. How does the profiling process help you in identifying and understanding the weak points in your application?

    Dengan melakukan profiling, saya berhasil menentukan bagian spesifik dalam program yang menjadi penyebab utama penurunan kinerja aplikasi. Hal ini memudahkan saya untuk menargetkan optimasi pada bagian tersebut, sehingga meningkatkan efisiensi aplikasi secara keseluruhan tanpa perlu melakukan perubahan luas pada komponen lain.

3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?
    
    Benar, dengan memanfaatkan Intellij profiler, saya menemukan bahwa sebagian program, seperti fungsi getAllStudentWithCourse, memerlukan iterasi yang berlebihan dan ini sangat mempengaruhi waktu eksekusi. Profiler ini memberikan kemampuan untuk mengetahui secara spesifik baris kode yang berkontribusi paling besar terhadap inefisiensi fungsi tersebut. Berbekal data tentang durasi eksekusi tiap-tiap pemanggilan fungsi, saya bisa dengan mudah menunjuk bagian program mana yang paling banyak menghambat efisiensi kinerja aplikasi secara umum.

4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?
    
    Salah satu tantangan utama dalam melakukan pengujian performa dan profiling adalah kemampuan untuk memahami dan menafsirkan output yang diberikan, serta menentukan komponen mana dalam program yang menjadi penghambat kinerja utama. Cara mengatasi masalah ini adalah dengan meningkatkan pemahaman terhadap hasil yang diberikan oleh alat seperti JMeter atau profiler. Ini mungkin membutuhkan periode adaptasi dengan teknologi tersebut untuk dapat menginterpretasikan data yang disajikan dengan lebih efektif dan detail.

5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?

    Menggunakan profiler dari IntelliJ membantu saya menemukan bagian program yang menyebabkan penundaan, memperoleh informasi tentang waktu yang diperlukan untuk sebuah metode dipanggil, serta mengukur seberapa sering metode tersebut dijalankan. Dengan data ini, kita bisa menargetkan area tertentu untuk dilakukan optimasi, sambil menghindari perubahan pada bagian yang tidak memerlukannya. Penting untuk diingat bahwa melakukan optimasi secara prematur dapat menimbulkan berbagai masalah, karena upaya optimasi yang dilakukan terlalu dini tidak hanya dapat menurunkan kejelasan kode, tapi juga berpotensi menimbulkan masalah tambahan yang tidak diinginkan.

6. How do you handle situations where the results from profiling with Inte	lliJ Profiler are not entirely consistent with findings from performance testing using JMeter?

    Sampai saat ini, hasil pengujian performa yang diperoleh dari IntelliJ Profiler dan JMeter menunjukkan konsistensi, tidak ada perbedaan yang signifikan antara keduanya. Hal ini menandakan bahwa kedua alat tersebut telah menyediakan analisis yang konsisten mengenai kinerja aplikasi dalam konteks pengujian kode yang saya lakukan.

7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?

    Mengacu pada strategi kedua, setelah menjalankan tes dan melakukan profiling, saya mengukur waktu respons program menggunakan JMeter. Jika ditemukan bahwa responsnya lambat, saya kemudian memanfaatkan profiler untuk mengidentifikasi elemen kode yang bertanggung jawab atas keterlambatan tersebut, dengan tujuan menemukan cara untuk mempercepat proses. Untuk memastikan bahwa modifikasi kode tidak mengubah output yang diharapkan, saya melakukan verifikasi untuk memastikan output setelah perubahan tetap sama dengan sebelumnya.

    Strategi yang lebih efisien mencakup penggunaan unit test, seperti yang dijelaskan dalam tutorial sebelumnya. Dengan implementasi dan keberhasilan unit test, saya bisa berasumsi bahwa kode yang direfaktori masih beroperasi dengan benar, asalkan unit test tersebut dirancang dengan baik dan sesuai. Pendekatan ini memungkinkan perhatian untuk tertuju pada perbaikan spesifik yang diperlukan, tanpa harus mengubah keseluruhan kode.