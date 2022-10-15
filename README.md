# Bank Target Marketing
Deposito merupakan salah satu investasi yang ada di bank dan merupakan salah satu cara bank untuk mendapatkan modal.Uang Anda diinvestasikan untuk tingkat bunga yang disepakati selama jangka waktu atau jangka waktu tertentu. kampanye melalui telepon merupakan salah satu cara untuk mendapatkan nasabah agar mau deposito berjangka. namun, di butuhkan investasi besar untuk melakukan kampanye itu dengan menyewa call center etc. oleh karena itu, sangat penting bagi kita untuk menidentifikasi pelanggan mana yang berpeluang untuk ikut deposito berjangka sehingga mereka dapat di targetkan terlebih dahulu untuk di lakukan kampanye, dan yang di identifikasi tidak iktu deposito berjangka agar tidak di lakukan kampanye, sehingga investasi kampanye dapat di lakukan efektif dan efisien.

## Partner
- Adelia Sekarsari
- Ahmad Zaky S.
- Andri Pradipta 
- Dear M. Ridlo
- Fathurrahman S 
- M Nurmayyahdi A
- Mirza Purta A
- Ricardo

## Methods Used
- Inferential Statistics
- Machine Learning
- Data Visualization
- Predictive Modeling
- etc.

## Technologies
- Python
- Pandas 
- jupyter
- numpy
- matplotlib
- seaborn
- google colab

## Prerequisite
1. download dataset [banking](https://www.kaggle.com/datasets/prakharrathi25/banking-dataset-marketing-targets)
2. install [Anaconda Navigator](https://www.anaconda.com/products/distribution)
3. atau dapat menggunakan [google colab](https://colab.research.google.com/)

## Project step
1. Preparation
2. EDA, Insight, & Visualization
3. Data Pre-Processing
4. Machine Learning Modeling & Evaluation
5. Final Preparation

### 1. Preparation
#### Problem Statement
Suatu bank yang ingin mengurangi cost terkait teller dan  marketing dengan mengkategorikan/pengelompokkan nasabah yang berprospek atau berpeluang membuka deposito.

#### Goals
Membuat model untuk mendeteksi user yang berpotensi membuka deposito, sehingga client tersebut akan diprioritaskan untuk diberikan marketing

#### Objective
Menurunkan Cost Marketing

#### Business Metrics
Meningkatkan conversion rate dan menurunkan cost Marketing

### 2. EDA, Insight, & Visualization
#### Descriptive Statistic
![My Image](src/df_info.png)

1. age (numeric)
2. job : type of job (categorical: "admin.","unknown","unemployed","management","housemaid","entrepreneur","student",
"blue-collar","self-employed","retired","technician","services")
3. marital : marital status (categorical: "married","divorced","single"; note: "divorced" means divorced or widowed)
4. education (categorical: "unknown","secondary","primary","tertiary")
5. default: has credit in default? (binary: "yes","no")
6. balance: average yearly balance, in euros (numeric)
7. housing: has housing loan? (binary: "yes","no")
8. loan: has personal loan? (binary: "yes","no")
9. contact: contact communication type (categorical: "unknown","telephone","cellular")
10. day: last contact day of the month (numeric)
11. month: last contact month of year (categorical: "jan", "feb", "mar", …, "nov", "dec")
12. duration: last contact duration, in seconds (numeric)
13. campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
14. pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric, -1 means client was not previously contacted)
15. previous: number of contacts performed before this campaign and for this client (numeric)
16. poutcome: outcome of the previous marketing campaign (categorical: "unknown","other","failure","success")
17. y - has the client subscribed a term deposit? (binary: "yes","no")

![My Image](src/missing_value.png)

terdapat beberapa yang ada missing value (job,education,contact,poutcome) yang semuanya categorical

![My Image](src/df_describe.png)
![My Image](src/count.png)


#### Univariate Statistic
##### Boxplot
![My Image](src/boxplot_1.png)

##### KDEplot
![My Image](src/kdeplot1.png)

##### Barplot
![My Image](src/barplot.png)
![My Image](src/barplot2.png)
![My Image](src/barplot3.png)

#### Multivariate Statistic
##### Heatmap
![My Image](src/heatmap1.png)
#### Business Insight
![My Image](src/bi1.png)

![My Image](src/bi2.png)

![My Image](src/bi3.png)

![My Image](src/bi4.png)

![My Image](src/bi5.png)

![My Image](src/bi6.png)

![My Image](src/bi7.png)

![My Image](src/bi8.png)

### 2. Data Pre-Processing
#### Data Cleansing
Unknown merupakan data dengan missing value pada Dataset Banking and Marketing

Pada variable job, kami melakukan drop data karena jumlah data relatif sedikit
Sedangkan pada variable education, contact, dan poutcome, kami menggunakan nilai modus untuk mengisi missing value dengan nilai terbanyak

#### Handling duplicated data
Tidak ada duplikasi data pada Dataset Banking and Marketing

#### Handling Outliers
untuk Handling Outliers kita menggunakan metode IQR untuk ['age'], Z-score untuk ['previous','duration','balance','campaign'] agar tidak terlalu banyak outlier yang di hapus jika menggunakan IQR semua

Sebelum Imputation
![My Image](src/boxplot_1.png)

Setelah Imputation
![My Image](src/boxplot_2.png)

Masih terdapat outlier pada beberapa varible. Hal ini disebabkan oleh penggunaan metode z-score yang tidak menghapus seluruh outlier. Akan tetapi, pemilihan metode ini dilakukan agar jumlah data yang mengaalami clensing tidak banyak atau kurang dari 10%. Setelah dilakukan cleansing, jumlah data menjadi 41444 yang sebelumnya sebanyak 44923 dimana persentase cleansing data sebanyak 7,7%

#### Feature Transformation
Log transformation

![My Image](src/log.png)
Setelah melakukan feature transformation terhadap ketiga metode, Kami memutuskan untuk mwnggunakan transformasi logaritma untuk variable balance dan duration, sedangkan untuk variable lainnya tidak dilakukan perubahan

#### Feature Encoding
##### 1.Label Encoding
![My Image](src/label.png)

kolom yang di ubah menggunakan label encoding adalah ['marital','education','default','housing','loan','contact','poutcome']

##### One-hot Encoding
![My Image](src/hot.png)

kolom yang di ubah menggunakan one-hot encoding adalah ['job','bulan']

## Reference
test edit
