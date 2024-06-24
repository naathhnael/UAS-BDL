# Tugas Akhir Mata Kuliah Basis Data

Project ini dibuat untuk memenuhi mata kuliah basis data. Project tentang basis data toko online bernama ShopEase.

## Entity Relationship Diagram

![Screenshot 2024-06-23 195011](https://github.com/naathhnael/UAS-BDL/assets/92132503/e53e9851-8017-413f-9320-08ad23dfc510)

ERD (Entity-Relationship Diagram) di atas menggambarkan relasi antara tabel-tabel dalam basis data "shopease." Tabel `products` berisi data produk dengan `category_id` yang mengacu ke tabel `categories` untuk pengelompokan kategori. Tabel `customers` menyimpan informasi pelanggan yang terkait dengan tabel `orders` melalui `customer_id`, menunjukkan setiap pesanan dibuat oleh pelanggan tertentu. Tabel `order_details` menghubungkan detail pesanan dengan `orders` melalui `order_id` dan dengan `products` melalui `product_id`, mencakup jumlah dan harga produk yang dipesan. Tabel `top_selling_products` mencatat produk terlaris berdasarkan total penjualan, meskipun tidak memiliki relasi langsung dalam diagram.

## Deskripsi Project
Project ini bernama ShopEase yaitu toko online, Fungsi dari basis data ini adalah untuk menampilkan `produk`, `kategori produk`, `detail order`, `order`, `customer` dan `produk terlaku`.

## Penjelasan Skema Basis Data
1. Pembuatan Trigger
![image (2)](https://github.com/naathhnael/UAS-BDL/assets/92132503/40d85398-1f4b-4e2b-8e0e-be019f0e794f)
Hasil Trigger
![Screenshot 2024-06-23 160806](https://github.com/naathhnael/UAS-BDL/assets/92132503/8ba28913-2c62-4b44-b1e0-78bfa44fb1c6)
2. Proses View
![image (3)](https://github.com/naathhnael/UAS-BDL/assets/92132503/b99cbd5b-9e42-4138-89e0-dd774275976d)
Hasil View
![image (4)](https://github.com/naathhnael/UAS-BDL/assets/92132503/43fac95e-073e-4826-b36d-793b0b749304)
3. Aggregate
![Screenshot 2024-06-23 162128](https://github.com/naathhnael/UAS-BDL/assets/92132503/9d22fe6d-874b-466a-98ab-384d5d66fa9b)
Untuk hasil diatas adalah total penjualan perbulan, dan hasil dibawah adalah rata-rata dari transaksi harian.
4. Left Join dan Inner Join
![Screenshot 2024-06-23 164326 (1)](https://github.com/naathhnael/UAS-BDL/assets/92132503/18d55a1d-1ea1-40fd-b521-0a6e329d27d9)
codingan diatas untuk menampilkan left join yang berisi `Customer id`, `Customer Name`, dan `Order Id`.
Sedangkan dibawahnya adalah inner join untuk menampilkan `Order Id`, `Product Id`, `Quantity`, dan `Produk Name`.
5. Subquery dan Having
![Screenshot 2024-06-23 164706](https://github.com/naathhnael/UAS-BDL/assets/92132503/3b91577f-9730-43ca-bc5c-5a58d9e49dc1)
Subquery `(SELECT AVG(price) FROM products)` menghitung harga rata-rata dari semua produk. Query utama kemudian mengambil nama dan harga produk yang harganya lebih tinggi dari harga rata-rata tersebut.
query menggabungkan tabel order_details dan products untuk menghitung total penjualan `(SUM(products.price * order_details.quantity))` per kategori produk `(products.category_id)`. Hasil tersebut kemudian dikelompokkan berdasarkan kategori produk `(GROUP BY products.category_id)`. Klausa HAVING HAVING total_sales > 1000 digunakan untuk menyaring kategori dengan total penjualan lebih dari 1000.
6. Wildcard
![Screenshot 2024-06-23 165306](https://github.com/naathhnael/UAS-BDL/assets/92132503/7b85c487-8990-4185-9265-88398e3445d7)
Wildcard disini saya gunakan untuk mencari data dalam tabel `products` dalam kolom `description` dan yang akan ditampilkan adalah kolom `product name` dan `description`.  
