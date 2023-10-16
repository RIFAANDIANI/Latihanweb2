### Penjelasan CSS
Cascading Style Sheet (CSS) merupakan aturan untuk mengatur beberapa komponen dalam sebuah web sehingga akan lebih terstruktur dan seragam. CSS bukan merupakan bahasa pemograman. CSS memudahkan dalam mengubah tampilan di berbagai halaman. Hanya dengan mengubah fungsi style di file CSS maka seluruh tampilan yang menggunakan fungsi tersebut akan berubah secara otomatis.

CSS mempunyai atribut lebih beragam dibandingkan dengan HTML CSS memungkinkan konten dapat dioptimasi di lebih dari satu perangkat. Hampir seluruh website yang ada di internet menggunakan CSS di dalamnya. Selain tampilannya yang lebih menarik, kebanyakan browser populer saat ini juga mendukung CSS.

## Struktur CSS
Perintah CSS terdiri atas 2 komponen, yakni Selector & Declaration. Selector berfungsi untuk memberi tahu browser bahwa pada elemen mana rule CSS diterapkan. Selector dapat berupa elemen HTML, selector class atau selector id. Declaration merupakan aturan CSS yang diterapkan, terdiri atas property dan value.
### PRAKTIKUM 2
1. Membuat dokumen HTML

```HTML
<!DOCTYPE html>
<html lang="en">

    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>CSS Dasar</title>
    </head>

    <body>
        <header>
            <h1>CSS Internal dan <i>Inline CSS</i></h1>
        </header>
        <nav>
            <a href="lab2_css_dasar.html">CSS Dasar</a>
            <a href="lab2_css_eksternal.html">CSS Eksternal</a>
            <a href="lab1_tag_dasar.html">HTML Dasar</a>
        </nav>
        <!-- CSS ID Selector -->
        <div id="intro">
            <h1>Hello World</h1>
            <p>Kami sedang belajar HTML dan CSS dasar, pada mata kuliah <b>Pemrograman
            Web</b> di <i>Universitas Pelita Bangsa</i>. Pelajaran pertama yang kami dapat
            adalah membuat tampilan web sederhana dalam rangka mengenal tag-tag dasar HTML
            dan CSS.</p>
            <!-- CSS Class Selector -->
            <a class="button btn-primary" href="#intro">Informasi selengkapnya.</a>
        </div>
    </body>
</html>
```

OUTPUT

![img.1](gambar/output%20dokumen%20html.png)

2. mendeklarasikan css internal
CODE

```HTML
<head>
    <title>CSS Dasar</title>
    <style>
    body {
    font-family:'Open Sans', sans-serif;
    }
    header {
    min-height: 80px;
    border-bottom:1px solid #77CCEF;
    }
    h1 {
    font-size: 24px;
    color: #0F189F;
    text-align: center;
    padding: 20px 10px;
    }
    h1 i {
    color:#6d6a6b;
    }
    </style>
</head>
```
![img.1](gambar/gambar%201.png)

3. MENAMBAHKAN inline CSS
CODE

```HTML
<p style="text-align: center; color: #ccd8e4;">
```
![img.1](gambar/gambar%202.png)
4. Membuat CSS Eksternal
- Buatlah file baru dengan nama style_eksternal.css kemudian buatlah deklarasi CSS seperti berikut.
code

```HTML
nav 
{
    background: #20A759;
    color:#fff;
    padding: 10px;
}
nav a 
{
    color: #fff;
    text-decoration: none;
    padding:10px 20px;
}
nav .active,
nav a:hover 
{
    background: #0B6B3A;

}
```
- Kemudian tambahkan tag untuk merujuk file css yang sudah dibuat pada bagian
Code :

```HTML
<head>
<!-- menyisipkan css eksternal -->
<link rel="stylesheet" href="style_eksternal.css" type="text/css">
</head>
```
OUTPUT
![img.1](gambar/gambar%203.png)

5. Menambahkan CSS Selector
Code :

```HTML
   /* ID Selector */
    #intro {
        background: #418fb1;
        border: 1px solid #099249;
        min-height: 100px;
        padding: 10px;
        }
        #intro h1 {
        text-align: left;
        border: 0;
        color: #fff;
        }
        /* Class Selector */
        .button {
        padding: 15px 20px;
        background: #bebcbd;
        color: #fff;
        display: inline-block;
        margin: 10px;
        text-decoration: none;
        }
        .btn-primary {
        background: #E42A42;
        }
```
OUTPUT
![img.1](gambar/gambar%204.png)

### PERTANYAAN
1. Lakukan eksperimen dengan mengubah dan menambah properti dan nilai pada kode CSS dengan mengacu pada CSS Cheat Sheet yang diberikan pada file terpisah dari modul ini
Code :

```HTML
/* ID Selector */
#intro {
    background: #b6bec2;
    border: 1px solid #941b2b;
    min-height: 100px;
    padding: 10px;
    }
    #intro h1 {
    text-align: left;
    border: 0;
    color: #810707;
    }
    /* Class Selector */
    .button {
    padding: 15px 20px;
    background: #3a2a32;
    color: #fff;
    display: inline-block;
    margin: 10px;
    text-decoration: none;
    }
    .btn-primary {
    background: #E42A42;
    }
```

![img.1](gambar/gambar%205.png)
2. Apa perbedaan pendeklarasian CSS elemen h1 {...} dengan #intro h1 {...}? berikan penjelasannya!
h1 {...} : Ini adalah contoh dari pendeklarasian CSS menggunakan elemen selektor (element selector). Dalam hal ini, gaya CSS akan diterapkan pada semua elemen h1 di seluruh halaman HTML yang sesuai dengan selektornya.

intro h1 {...}: Ini adalah contoh dari pendeklarasian CSS menggunakan selektor kombinasi (descendant selector). Dalam hal ini, gaya CSS akan diterapkan pada semua elemen h1 yang berada dalam elemen dengan ID "intro".
3. Apabila ada deklarasi CSS secara internal, lalu ditambahkan CSS eksternal dan inline CSS pada elemen yang sama. Deklarasi manakah yang akan ditampilkan pada browser? Berikan penjelasan dan contohnya!
Ketika Anda memiliki beberapa deklarasi CSS untuk elemen yang sama, ada beberapa aturan yang menentukan urutan prioritas dan mana yang akan diterapkan pada elemen tersebut. Aturan ini disebut dengan "Cascading Order" atau "Urutan Cascading" dan mengikuti prinsip berikut:

- Inline CSS: Deklarasi CSS yang diberikan secara inline langsung pada elemen HTML akan memiliki prioritas tertinggi.
- Internal CSS: Deklarasi CSS yang ada dalam tag style di dalam elemen HTML akan diterapkan setelah aturan inline.
- Eksternal CSS: Aturan CSS dari file eksternal yang dihubungkan ke halaman HTML akan diterapkan setelah aturan internal.
4. Pada sebuah elemen HTML terdapat ID dan Class, apabila masing-masing selector tersebut terdapat deklarasi CSS, maka deklarasi manakah yang akan ditampilkan pada browser? Berikan penjelasan dan contohnya!
- ID Selector: ID memiliki tingkat spesifikitas yang lebih tinggi daripada class. Oleh karena itu, jika ada konflik antara ID dan class, aturan yang dideklarasikan dengan menggunakan ID akan diikuti.

- Class Selector: Class memiliki tingkat spesifikitas yang lebih rendah daripada ID. Ini berarti jika ada konflik antara ID dan class, aturan yang dideklarasikan menggunakan class akan digantikan oleh aturan yang dideklarasikan menggunakan ID.
```HTML
<!DOCTYPE html>
<html>
<head>
  <style>
    #heading {
      color: red; /* Deklarasi CSS dengan ID */
    }

    .special {
      color: blue; /* Deklarasi CSS dengan class */
    }
  </style>
</head>
<body>
  <h1 id="heading" class="special">Ini adalah teks dengan warna.</h1>
</body>
</html>
```
### SELESAI