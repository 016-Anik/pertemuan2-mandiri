## A. Postman GET $BASE

### Request

```text
GET https://silab.ft.unira.ac.id/api/v1

Request menggunakan method GET ke endpoint $BASE.

Hasil Pengujian
HTTP/1.1 301 Moved Permanently
Location: /api/v1/

Status 301 Moved Permanently menunjukkan bahwa endpoint /api/v1 mengarahkan request ke /api/v1/.

Setelah diarahkan ke /api/v1/, response yang diterima berupa halaman HTML pemberitahuan dari Universitas Madura. Halaman tersebut menjelaskan bahwa SILAB telah berpindah ke ATLAS.

Isi response menunjukkan:

SILAB telah berpindah ke ATLAS

Layanan di silab.ft.unira.ac.id sudah dialihkan ke alamat baru
atlas.unira.ac.id.

Silakan perbarui bookmark Anda.

Alamat sistem baru yang ditampilkan pada response adalah:

https://atlas.unira.ac.id

Response HTML juga menyediakan tombol "Lanjut ke ATLAS Sekarang" dan pengalihan otomatis menuju ATLAS.

Pada Postman, bagian Pretty digunakan untuk melihat isi response HTML, sedangkan bagian Headers digunakan untuk melihat informasi header HTTP seperti status code, content type, server, dan informasi lainnya.

Kesimpulan A

Pengujian GET $BASE menunjukkan bahwa endpoint /api/v1 memberikan status 301 Moved Permanently dan mengarahkan request ke /api/v1/. Setelah diarahkan, halaman memberikan informasi bahwa layanan SILAB Universitas Madura telah berpindah ke sistem baru yaitu ATLAS pada https://atlas.unira.ac.id.

## B. DevTools Network

Halaman yang diuji:

https://silab.ft.unira.ac.id/jadwal

Pengujian dilakukan menggunakan DevTools pada browser dengan membuka halaman `/jadwal` dan melihat request yang dikirim melalui tab Network.

Request API:

POST /api/v1/graphql

Request URL:

https://silab.ft.unira.ac.id/api/v1/graphql

Status Code: 200

Status: OK

Hasil pengujian menunjukkan bahwa halaman `/jadwal` melakukan request ke endpoint `/api/v1/graphql` menggunakan method POST. Request tersebut berhasil diproses oleh server dan menghasilkan status `200 OK`.

## C. curl -i $BASE/salah-ketik

Command:

curl -i https://silab.ft.unira.ac.id/api/v1/salah-ketik

Hasil pengujian:

HTTP/1.1 404 Not Found

Status Code: 404

Status: Not Found

Message: Api atau berkas tidak ditemukan

Server: nginx

Framework: Express

Hasil pengujian menunjukkan bahwa request ke endpoint `/api/v1/salah-ketik` menghasilkan status `404 Not Found`. Response dari server juga menampilkan message `Api atau berkas tidak ditemukan`.

