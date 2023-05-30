# e-COMMERCE

### I Made Pringga Putra Baskara
2205551123

## About
Program ini membantu para mahasiswa untuk belajar membuat backend API untuk aplikasi e-commerce sederhana yang nantinya memberikan response dengan format JSON. Adapun request method pada API memuat: <br/>
**GET** untuk mendapatkan list atau detail data dari entitas. <br/>
**POST** untuk membuat data entitas baru. <br/>
**PUT** untuk mengubah data dari entitas. <br/>
**DELETE** untuk menghapus data dari entitas. <br/>

Data-data yang digunakan dalam aplikasi e-Commerce ini yang nantinya akan disimpan pada **database SQLite** yang kemudian akan dilakukan suatu pengujian API yang telah diprogram melalui aplikasi **Postman**

## Spesifikasi API dalam Aplikasi e-Commerce
### **GET**

- GET /users untuk mendapatkan daftar semua user yang termuat di dalam database. <br/>
```
    {
    "User Information": [
        {
            "First_Name": "John",
            "Type": "buyer",
            "Email": "johndoe@example.com",
            "Last_Name": "Doe",
            "id_user": 1,
            "Phone Number": "123456789"
        },
        {
            "First_Name": "Jane",
            "Type": "seller",
            "Email": "janesmith@example.com",
            "Last_Name": "Smith",
            "id_user": 2,
            "Phone Number": "987654321"
        },
        {
            "First_Name": "Michael",
            "Type": "buyer",
            "Email": "michaeljohnson@example.com",
            "Last_Name": "Johnson",
            "id_user": 3,
            "Phone Number": "456789123"
        },
        {
            "First_Name": "made",
            "Type": "seller",
            "Email": "sojibuah@example.com",
            "Last_Name": "Dwita",
            "id_user": 4,
            "Phone Number": "934701270"
        },
        {
            "First_Name": "ketut",
            "Type": "seller",
            "Email": "kitabangunbersama@example.com",
            "Last_Name": "nyamprut",
            "id_user": 5,
            "Phone Number": "089999111"
        }
    ]
}
```

```(localhost:8123/users)```

<br/>

- GET /users/{id} untuk mendapatkan informasi user dan alamatnya. <br/>
```
{
    "User Information": [
        {
            "First_Name": "John",
            "Type": "buyer",
            "Email": "johndoe@example.com",
            "Last_Name": "Doe",
            "Id": 1,
            "City": "Jakarta",
            "Phone Number": "123456789",
            "Postcode": "12345",
            "Province": "DKI Jakarta"
        }
    ]
}
```

```localhost:8123/users/1```

<br/>

- GET /users/{id}/products untuk mendapatkan daftar produk milik user. <br/>
```
{
    "Products Information": [
        {
            "User ID": 4,
            "Nama": "made",
            "Harga": 300000,
            "Deskripsi": "Celana keren untuk kegiatan seharian mu",
            "ID Barang": 3,
            "Nama Produk": "Celana Carpenter",
            "Stock": 5
        },
        {
            "User ID": 4,
            "Nama": "made",
            "Harga": 12000,
            "Deskripsi": "buah segar dari ladangnya",
            "ID Barang": 4,
            "Nama Produk": "Semangka",
            "Stock": 30
        }
    ]
}
```

``` localhost:8123/users/4/products ```
<br/>

- GET /users/{id}/orders untuk mendapatkan daftar order milik user. <br/>
```
{
    "Order Information": [
        {
            "Order": 1,
            "Nama": "Jane",
            "Total": 4,
            "Diskon": 0,
            "id user": 2
        },
        {
            "Order": 2,
            "Nama": "Jane",
            "Total": 5,
            "Diskon": 0,
            "id user": 2
        }
    ]
}
```

``` localhost:8123/users/2/orders```

<br/>

- GET /users/{id}/reviews untuk mendapatkan daftar review yang dibuat oleh user. <br/>
```
{
    "Reviews Information": [
        {
            "User": 2,
            "star": 5,
            "First Name": "Jane",
            "Deskripsi": "customer merasa senang karena admin sangat baik",
            "Last Name": "Smith",
            "order": 1
        },
        {
            "User": 2,
            "star": 4,
            "First Name": "Jane",
            "Deskripsi": "admin ramah",
            "Last Name": "Smith",
            "order": 2
        }
    ]
}
```

```localhost:8123/users/2/reviews```

<br/>

- GET /orders/{id} untuk mendapatkan informasi order, buyer, detail order, review, product title, beserta pricenya. <br/>
```  
- {
  "Orders Information": [
  {
  "idUser": 2,
  "idOrder": 1,
  "Description": "customer merasa senang karena admin sangat baik",
  "Price": "48000",
  "Star": 5,
  "Note": 19283746,
  "idProduct": 4,
  "Quantity": 4,
  "Title": "Semangka",
  "Name": "Jane"
  }
  ]
  }
```

``` localhost:8123/orders/1 ```
<br/>

- GET /products untuk mendapatkan daftar semua produk. <br/>

``` {
    "Product Information": [
        {
            "Description": "minuman segar saat panas",
            "User": 2,
            "Price": "8000",
            "Title": "Buavita",
            "Id": 1,
            "Stock": 10
        },
        {
            "Description": "Coklat murni yang manis",
            "User": 2,
            "Price": "2000",
            "Title": "Beng beng",
            "Id": 2,
            "Stock": 20
        },
        {
            "Description": "Celana keren untuk kegiatan seharian mu",
            "User": 4,
            "Price": "300000",
            "Title": "Celana Carpenter",
            "Id": 3,
            "Stock": 5
        },
        {
            "Description": "buah segar dari ladangnya",
            "User": 4,
            "Price": "12000",
            "Title": "Semangka",
            "Id": 4,
            "Stock": 30
        },
        {
            "Description": "Kue untuk ultah mu",
            "User": 5,
            "Price": "120000",
            "Title": "Kue BlackForest",
            "Id": 5,
            "Stock": 10
        }
    ]
}
```

``` localhost:8123/products ```
<br/>

- GET /products/{id} untuk mendapatkan informasi produk dan seller. <br/>

``` {
    "Product Information": [
        {
            "First_Name": "Jane",
            "Type": "seller",
            "Description": "minuman segar saat panas",
            "Email": "janesmith@example.com",
            "Price": "8000",
            "Last_Name": "Smith",
            "Title": "Buavita",
            "Seller": 2,
            "Id": 1,
            "id_user": 2,
            "Phone Number": "987654321",
            "Stock": 10
        },
        {
            "First_Name": "Jane",
            "Type": "seller",
            "Description": "Coklat murni yang manis",
            "Email": "janesmith@example.com",
            "Price": "2000",
            "Last_Name": "Smith",
            "Title": "Beng beng",
            "Seller": 2,
            "Id": 2,
            "id_user": 2,
            "Phone Number": "987654321",
            "Stock": 20
        }
    ]
}
```
<br/>

### **POST**
- Membuat entitas baru berupa tabel ... <br/>
``` {
    "first_name" : "John",
    "last_name" : "Doe",
    "email": "johndoe@example.com",
    "phone_number" : "123456789",
    "type" : "buyer"
}
```

``` localhost:8123/users ```

<br/>
### **PUT**
- Mengubah entitas yang ada dimana user mengubah entitas pada ... <br/>

```
{
    "first_name" : "John",
    "last_name" : "Doe",
    "email": "johndoe@example.com",
    "phone_number" : "123456789",
    "type" : "buyer"
}
```
``` localhost:8123/users/1 ```
<br/>

### **DELETE**
- Menghapus data dari entitas tertentu dimana user mencoba untuk menghapus data yang terdapat didalam tabel ... <br/>

``` localhost:8123/users/1 ```
<br/>

### PENUTUP ###
SUKSMA MATUR NUHUN