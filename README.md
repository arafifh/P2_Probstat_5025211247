# P2_Probstat_5025211247

### Nama : Ahmad Rafif Hikmatiar
### NRP  : 5025211247



## Nomor 1

### a
```R
sebelumAktivitasA <- c(78, 75, 67, 77, 70, 72, 78, 74, 77)
setelahAktivitasA <- c(100, 95, 70, 90, 90, 90, 89, 90, 100)
tabelPengamatanOksigen <- data.frame (
  x = sebelumAktivitasA,
  y = setelahAktivitasA
)

tabelPengamatanOksigen

perbedaanSesudahDanSebelum <- tabelPengamatanOksigen[["y"]] - tabelPengamatanOksigen[["x"]]
n <- length(perbedaanSesudahDanSebelum)
rerata <- mean(perbedaanSesudahDanSebelum)

variance <- 0

for (i in perbedaanSesudahDanSebelum) {
  variance <- variance + (i - rerata)^2 
}
variance <- variance / (n - 1)
standardDeviasi <- variance^(0.5)

standardDeviasi
```
![Screenshot 2022-12-13 204149](https://user-images.githubusercontent.com/89500557/207358023-8eacada9-181f-4d58-952a-cbd9691dedbe.png)

Standard deviasi adalah 6.359595


### b
```R
t.test(
  x = perbedaanSesudahDanSebelum, alternative="two.sided",
  mu=0, var.equal=TRUE
)
```
![Screenshot 2022-12-13 204223](https://user-images.githubusercontent.com/89500557/207358173-efd33cd3-5c55-4cd3-a2ab-7ad4d7c8be84.png)

karena harus mencari nilai t tanpa diketahui significant level, maka
significant  level yang digunakan adalah 0,05 (seperti pada poin c)
yaitu nilainya adalah t = 7,6525 dan p-value = 6.003e-5


### c
```R
meanPerubahan = 0
significantLevel <- 0.05
t <- (rerata - meanPerubahan) * (n^(0.5)) / standardDeviasi
if (2 * dt(t, n - 1) <= significantLevel) {
  print("Menolak H0, terdapat pengaruh")
} else {
  print("Tidak menolak H0, tidak terdapat pengaruh")
}
```
![Screenshot 2022-12-13 204335](https://user-images.githubusercontent.com/89500557/207358205-df0631d0-5deb-4c8c-9ea6-5979c4a73182.png)

H0 ditolak, terdapat pengaruh pada kadar saturasi oksigen yang disebabkan aktivitas A


## Nomor 2
```R
library(BSDA)

zsum.test(
  mean.x=23500, sigma.x = 3900, n.x = 100,  
  alternative = "two.sided", mu = 20000,
  conf.level = 0.95
)
```
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
```R
confidenceLevel <- 0.95
n1 = 19
mean1 = 3.64
sigma1 = 1.67

n2 = 27
mean2 = 2.79
sigma2 = 1.32

sp <- (((n1 - 1)*(sigma1^2) + (n2 - 1)*(sigma2^2)) / (n1 + n2 - 2))^(0.5)

dof <- n1 + n2 - 2
paste("s-pool: ", sp)
```
![3b](https://user-images.githubusercontent.com/89500557/207359883-695d5d4a-8de8-4d38-98f0-d09f79a1c486.png)

s-pool yang didapatkan adalah 1,473266


### c
```R
tsum.test (
  mean.x=mean1, s.x = sigma1, n.x = n1, 
  mean.y=mean2, s.y = sigma2, n.y = n2, 
  alternative = "two.sided", 
  mu = 0, var.equal = TRUE,
  conf.level = confidenceLevel
)
```
p-value = 0.06049 dan t = 1,9267


### d

Nilai kritikal adalah 0.05 dan p-value adalah 0.06049


### e

Terima null hipotesa


### f

Rata-rata kedua populasi sama, tidak cukup bukti untuk menyatakan terdapat 
perbedaan pada rata-rata kedua populasi 


## Nomor 4
```R
Kucing <- read.table("https://rstatisticsandresearch.weebly.com/uploads/1/0/2/6/1026585/onewayanova.txt", header = TRUE)
Kucing$Group <- as.factor(Kucing$Group)
Kucing$Group <- factor(Kucing$Group, labels = c("Oren", "Hitam", "Putih"))
```
### a
```R
Group1 <- subset(Kucing, Group == "Oren")
Group2 <- subset(Kucing, Group == "Hitam")
Group3 <- subset(Kucing, Group == "Putih")

qqnorm(Group1$Length, col = "orange")
qqline(Group1$Length, col = "orange")

qqnorm(Group2$Length, col = "black")
qqline(Group2$Length, col = "black")

qqnorm(Group3$Length, col = "red")
qqline(Group3$Length, col = "red")
```
Untuk mengerjakan soal 4a ini, kita harus import dataset terlebih dahulu karena dataset ini berasal dari <i>website<i>
![4a](https://user-images.githubusercontent.com/89500557/207360296-97e19d29-ef4c-44f0-b114-c891cceb2298.png)
![4a(1)](https://user-images.githubusercontent.com/89500557/207360323-582fd0c3-c4d6-4319-b567-d0d605784f68.png)
![4a(2)](https://user-images.githubusercontent.com/89500557/207360330-3c9a4a6e-9404-4d2e-9753-0c61197ce928.png)

### b
  ```R
  bartlett.test(Length ~ Group, data = Kucing)
```
![4b](https://user-images.githubusercontent.com/89500557/207361281-0d0e7c3a-1fbe-451e-91ac-aafa3cfb9a54.png)

H0 : variansi ketiga populasi sama

H1 : variansi ketiga populasi berbeda

p-value = 0,8054

significant level = 0,05

Null hipotesis diterima karena nilai p-value lebih besar dari significant level, variansi ketiga populasi sama


### c
```R
  model1 <- aov(Length ~ Group, data = Kucing)
summary(model1)
```
![4c](https://user-images.githubusercontent.com/89500557/207361736-11fd55a1-8def-49fd-874c-567a68aa7526.png)


### d
```R
            summary(model1)
            ```
H0 : mean1 = mean2 = mean3

H1 : mean1 != mean2 != mean3

p-value = 0.0013

Keputusan: Tolak H0, karena p-value < 0.05

Kesimpulan: rata-rata ketiga populasi berbeda


### e
```R
  TukeyHSD(model1)
  ```
![4e](https://user-images.githubusercontent.com/89500557/207362262-22ac8b92-4b60-4ec8-9e70-1d5718d3e866.png)

Terdapat perbedaan pada kucing grup 1 dengan grup 2 dan kucing grup 2 dengan grup 3 sedangkan grup 1 dengan grup 3 sama, kucing grup 2 adalah yang terpendek


### f
```R
  install.packages("ggplot2")
library("ggplot2")

ggplot(Kucing, aes(x = Group, y = Length)) + 
  geom_boxplot(fill = "Yellow", colour = "Black") + 
  scale_x_discrete() + xlab("Jenis Kucing") + ylab("Panjang Kucing (cm)")
  ```
![4f](https://user-images.githubusercontent.com/89500557/207362669-753707f9-ee19-4b3a-886c-196b0610ba0b.png)


## Nomor 5
```R
  install.packages("multcompView")
install.packages("readr")
install.packages("dplyr")
library(readr)
library(ggplot2)
library(multcompView)
library(dplyr)

ExpData <- read.csv("https://drive.google.com/u/0/uc?id=1aLUOdw_LVJq6VQrQEkuQhZ8FW43FemTJ&export=download")
ExpData$Glass <- as.factor(ExpData$Glass)
ExpData$Temp <- as.factor(ExpData$Temp)
```
### a
```R
                qplot(x = Temp, y = Light, data = ExpData) + facet_grid(.~Glass) + geom_point()
```
![5a](https://user-images.githubusercontent.com/89500557/207362971-145ffcdc-bbd2-434f-affa-5be9e1378d72.png)


### b
```R
AnnovaCahaya <- aov(Light ~ Glass + Temp + Glass:Temp, ExpData)
summary(AnnovaCahaya)
```
Untuk menyelesaikan soal ini, kita harus menguji dengan uji annova 2 arah dan dengan 2 faktor.
![5b](https://user-images.githubusercontent.com/89500557/207363087-d5ffe6ed-42a5-44e9-80d9-b84c26551aa8.png)


### c
```R
  group_by(ExpData, Glass, Temp) %>% summarise(mean=mean(Light), sd=sd(Light))
```
Penyelesaian ini membutuhkan fungsi <i>group_by<i> dan <i>summarise<i> untuk membuat plottingan data sesuai dengan yang diminta oleh soal
![5c](https://user-images.githubusercontent.com/89500557/207363212-5369795b-290e-45fb-be1a-b78ee1b34fb3.png)


### d
```R
  hasilTukeyCahaya <- TukeyHSD(AnnovaCahaya)
hasilTukeyCahaya
```
Di soal ini saya memakai fungsi <i>Tukey<i> dengan parameter <i>AnnovaCahaya<i>
![5d](https://user-images.githubusercontent.com/89500557/207363241-b096cbd1-87c7-46df-bec6-a07ff941b056.png)


### e
```R
multcompLetters4(AnnovaCahaya, hasilTukeyCahaya)
```
Saya menggunakan fungsi <i>multcompLetters4<i> untuk mengerjakan soal ini
![5e](https://user-images.githubusercontent.com/89500557/207363256-639c602f-906c-46b4-b9c4-68ed2a51eb6c.png)
