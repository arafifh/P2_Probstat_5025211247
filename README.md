# P2_Probstat_5025211247

### Nama : Ahmad Rafif Hikmatiar
### NRP  : 5025211247



## Nomor 1

### a

![Screenshot 2022-12-13 204149](https://user-images.githubusercontent.com/89500557/207358023-8eacada9-181f-4d58-952a-cbd9691dedbe.png)

Standard deviasi adalah 6.359595


### b

![Screenshot 2022-12-13 204223](https://user-images.githubusercontent.com/89500557/207358173-efd33cd3-5c55-4cd3-a2ab-7ad4d7c8be84.png)

karena harus mencari nilai t tanpa diketahui significant level, maka
significant  level yang digunakan adalah 0,05 (seperti pada poin c)
yaitu nilainya adalah t = 7,6525 dan p-value = 6.003e-5


### c

![Screenshot 2022-12-13 204335](https://user-images.githubusercontent.com/89500557/207358205-df0631d0-5deb-4c8c-9ea6-5979c4a73182.png)

H0 ditolak, terdapat pengaruh pada kadar saturasi oksigen yang disebabkan aktivitas A


## Nomor 2


### a

H0 : mean = 20000

H1 : mean != 20000

Tidak setuju


### b

Nilai p-value < 2.2e-16 dan estimasi rentang rata-ratanya adalah 22735.61 < mean < 24264.39

### c

Null hipotesis ditolak karena nilai p-value lebih kecil dari significant level

## Nomor 3

### a

H0 : rata-rata Bandung - rata-rata Bali = 0

H1 : rata-rata Bandung - rata-rata Bali != 0


### b

![3b](https://user-images.githubusercontent.com/89500557/207359883-695d5d4a-8de8-4d38-98f0-d09f79a1c486.png)

s-pool yang didapatkan adalah 1,473266


### c

p-value = 0.06049 dan t = 1,9267


### d

Nilai kritikal adalah 0.05 dan p-value adalah 0.06049


### e

Terima null hipotesa


### f

Rata-rata kedua populasi sama, tidak cukup bukti untuk menyatakan terdapat 
perbedaan pada rata-rata kedua populasi 


## Nomor 4

### a
Untuk mengerjakan soal 4a ini, kita harus import dataset terlebih dahulu karena dataset ini berasal dari <i>website<i>
![4a](https://user-images.githubusercontent.com/89500557/207360296-97e19d29-ef4c-44f0-b114-c891cceb2298.png)
![4a(1)](https://user-images.githubusercontent.com/89500557/207360323-582fd0c3-c4d6-4319-b567-d0d605784f68.png)
![4a(2)](https://user-images.githubusercontent.com/89500557/207360330-3c9a4a6e-9404-4d2e-9753-0c61197ce928.png)

### b

![4b](https://user-images.githubusercontent.com/89500557/207361281-0d0e7c3a-1fbe-451e-91ac-aafa3cfb9a54.png)

H0 : variansi ketiga populasi sama

H1 : variansi ketiga populasi berbeda

p-value = 0,8054

significant level = 0,05

Null hipotesis diterima karena nilai p-value lebih besar dari significant level, variansi ketiga populasi sama


### c

![4c](https://user-images.githubusercontent.com/89500557/207361736-11fd55a1-8def-49fd-874c-567a68aa7526.png)


### d

H0 : mean1 = mean2 = mean3

H1 : mean1 != mean2 != mean3

p-value = 0.0013

Keputusan: Tolak H0, karena p-value < 0.05

Kesimpulan: rata-rata ketiga populasi berbeda


### e

![4e](https://user-images.githubusercontent.com/89500557/207362262-22ac8b92-4b60-4ec8-9e70-1d5718d3e866.png)

Terdapat perbedaan pada kucing grup 1 dengan grup 2 dan kucing grup 2 dengan grup 3 sedangkan grup 1 dengan grup 3 sama, kucing grup 2 adalah yang terpendek


### f

![4f](https://user-images.githubusercontent.com/89500557/207362669-753707f9-ee19-4b3a-886c-196b0610ba0b.png)


## Nomor 5

### a

![5a](https://user-images.githubusercontent.com/89500557/207362971-145ffcdc-bbd2-434f-affa-5be9e1378d72.png)


### b
Untuk menyelesaikan soal ini, kita harus menguji dengan uji annova 2 arah dan dengan 2 faktor.
![5b](https://user-images.githubusercontent.com/89500557/207363087-d5ffe6ed-42a5-44e9-80d9-b84c26551aa8.png)


### c

Penyelesaian ini membutuhkan fungsi <i>group_by<i> dan <i>summarise<i> untuk membuat plottingan data sesuai dengan yang diminta oleh soal
![5c](https://user-images.githubusercontent.com/89500557/207363212-5369795b-290e-45fb-be1a-b78ee1b34fb3.png)


### d

Di soal ini saya memakai fungsi <i>Tukey<i> dengan parameter <i>AnnovaCahaya<i>
![5d](https://user-images.githubusercontent.com/89500557/207363241-b096cbd1-87c7-46df-bec6-a07ff941b056.png)


### e

Saya menggunakan fungsi <i>multcompLetters4<i> untuk mengerjakan soal ini
![5e](https://user-images.githubusercontent.com/89500557/207363256-639c602f-906c-46b4-b9c4-68ed2a51eb6c.png)
