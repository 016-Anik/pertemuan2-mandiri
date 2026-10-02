# TM-2 — Kartu HTTP Method + Code

Entity: Peminatan
BASE API: `https://silab.ft.unira.ac.id/api/v1`

---

## 1. Tabel Analisis Rapor HTTP

| Endpoint / Request | Method | Status Code & Message | Siapa Salah? | Aksi Perbaikan |
|---|---|---|---|---|
| `GET /api/v1/peminatan` | `GET` | **200 OK** <br> *"Data peminatan berhasil diambil"* | Tidak ada | Data berhasil ditarik dari database dan dikembalikan ke client dalam format JSON. |
| `POST /api/v1/peminatan/pilih` | `POST` | **201 Created** <br> *"Pilihan peminatan berhasil disimpan"* | Tidak ada | Resource baru berhasil dibuat. Pilihan peminatan mahasiswa tersimpan di database. |
| `POST /api/v1/peminatan/pilih` | `POST` | **400 Bad Request** <br> *"Peminatan ID wajib diisi"* | **Client** | Client mengirim request body tanpa field `specialization_id`. Perbaiki payload JSON pada client/Postman. |
| `GET /api/v1/peminatan/statistik` | `GET` | **401 Unauthorized** <br> *"Token JWT tidak ditemukan atau kadaluwarsa"* | **Client** | Client mencoba mengakses endpoint terproteksi tanpa menyertakan `Bearer Token` pada header request. Tambahkan token valid. |
| `GET /api/v1/peminatan/admin-only` | `GET` | **403 Forbidden** <br> *"Role Mahasiswa tidak memiliki akses"* | **Client** | Client menggunakan token mahasiswa untuk mengakses endpoint khusus Kaprodi/Tendik. Login ulang menggunakan akun dengan role yang sesuai. |
| `GET /api/v1/peminatan/500-test` | `GET` | **500 Internal Server Error** <br> *"Database connection failed"* | **Server** | Terjadi kegagalan koneksi database/unhandled exception pada logika backend. Cek log server/backend service. |

---

## 2. Kartu Rapor HTTP Detail (Sesuai Soal)

### 1. `GET /api/v1/peminatan`
- **Method**: `GET`
- **Status Code**: `200 OK`
- **Message**: `"Data peminatan berhasil diambil"`
- **Siapa Salah**: Tidak ada kesalahan.
- **Aksi Perbaikan**: Tidak perlu tindakan perbaikan. Server berhasil mereturn daftar peminatan.

---

### 2. `GET /jadwal/jumlah-jadwal`
- **Method**: `GET`
- **Status Code**: `401 Unauthorized` / `403 Forbidden`
- **Message**: `"Authentication required / Invalid API key"`
- **Siapa Salah**: **Client**
- **Aksi Perbaikan**: Client mengirimkan request tanpa kredensial/API Key yang valid pada header `Authorization`. Sertakan token/API key yang tepat.

---

### 3. `POST /jadwal`
- **Method**: `POST`
- **Status Code**: `201 Created`
- **Message**: `"Jadwal baru berhasil ditambahkan"`
- **Siapa Salah**: Tidak ada kesalahan.
- **Aksi Perbaikan**: Data jadwal baru berhasil diproses dan disimpan oleh server.

---

### 4. `GET /api/v1/xxx`
- **Method**: `GET`
- **Status Code**: `404 Not Found`
- **Message**: `"Route /api/v1/xxx tidak ditemukan"`
- **Siapa Salah**: **Client**
- **Aksi Perbaikan**: Client memanggil URL/route yang tidak terdaftar pada API router. Ubah URL endpoint sesuai dengan peta routing API yang valid.

---

### 5. `POST https://api.unira.ac.id/graphql`
- **Method**: `POST`
- **Status Code**: `400 Bad Request` / `200 OK` *(dengan `errors` payload)*
- **Message**: `"Syntax Error: Cannot query field 'unknownField' on type 'Query'"`
- **Siapa Salah**: **Client**
- **Aksi Perbaikan**: Client mengirimkan GraphQL query yang tidak sesuai dengan schema. Perbaiki struktur GraphQL document/query pada request body.



