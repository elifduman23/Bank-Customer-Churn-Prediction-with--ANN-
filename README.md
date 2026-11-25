# Bank Customer Churn Prediction with ANN / Yapay Sinir Ağları ile Banka Müşteri Kaybı Tahmini

---

## 🇹🇷 Türkçe

### Proje Hakkında
Bu proje, **Yapay Sinir Ağları (ANN)** kullanarak bir bankanın müşterilerinin bankadan ayrılıp ayrılmayacağını (churn) tahmin etmeyi amaçlar. Model, Keras ve TensorFlow kullanılarak oluşturulmuş ve **Bank Customer Churn Prediction (`Churn_Modelling.csv`)** veri seti üzerinde eğitilmiştir.

### Veri Seti
* **Kaynak:** Kaggle – Bank Customer Churn Prediction (`Churn_Modelling.csv`)
* **Boyut:** 10.000 satır, 14 sütun (eksik veri bulunmamaktadır)
* **Kullanılan Özellikler (X):** `CreditScore`, `Geography`, `Gender`, `Age`, `Tenure`, `Balance`, `NumOfProducts`, `HasCrCard`, `IsActiveMember`, `EstimatedSalary`
* **Hedef Değişken (y):** `Exited` (`0`: Müşteri kaldı, `1`: Müşteri ayrıldı)

### Veri Ön İşleme Adımları
1. `RowNumber`, `CustomerId` ve `Surname` sütunları modelle ilgisiz olduğu için çıkarıldı.
2. Kategorik değişkenler (`Geography` ve `Gender`) `LabelEncoder` ve `OneHotEncoder(drop='first')` ile sayısal formata dönüştürüldü (toplam 11 girdi özelliği).
3. Veri seti **%75 eğitim / %25 test** olarak ayrıldı (`random_state=60`).
4. Özellikler `StandardScaler` ile ölçeklendirildi.

### Model Mimarisi
Keras `Sequential` API ile oluşturulan yapay sinir ağı mimarisi:
* **1. Gizli Katman:** 4 nöron, `ReLU` aktivasyon fonksiyonu (`input_dim=11`)
* **2. Gizli Katman:** 4 nöron, `ReLU` aktivasyon fonksiyonu
* **3. Gizli Katman:** 4 nöron, `ReLU` aktivasyon fonksiyonu
* **Çıkış Katmanı:** 1 nöron, `Sigmoid` aktivasyon fonksiyonu
* **Toplam Parametre Sayısı:** 93

### Eğitim Parametreleri ve Sonuçlar
* **Optimizer:** Adam
* **Loss Function:** `binary_crossentropy`
* **Epochs:** 10
* **Batch Size:** 10
* **Eğitim Doğruluğu (Epoch 10/10):** `%83.19` (`accuracy: 0.8319`, `loss: 0.4060`)

### Model Çıktısı
<img width="980" height="337" alt="Ekran görüntüsü 2026-11-25 090320" src="https://github.com/user-attachments/assets/49351076-15cc-4ad5-b38c-47400e666d82" />



<img width="1035" height="657" alt="Ekran görüntüsü 2026-11-25 091019" src="https://github.com/user-attachments/assets/22263269-9cfc-4530-853f-6106b9e7615c" />


### Kullanılan Teknolojiler
* Python
* NumPy & Pandas
* Scikit-learn
* TensorFlow / Keras
* Matplotlib & Seaborn

---

## 🇬🇧 English

### About the Project
This project predicts whether a bank's customers will leave the bank (customer churn) using an **Artificial Neural Network (ANN)**. The model is built with Keras and TensorFlow and trained on the **Bank Customer Churn Prediction (`Churn_Modelling.csv`)** dataset.

### Dataset
* **Source:** Kaggle – Bank Customer Churn Prediction (`Churn_Modelling.csv`)
* **Shape:** 10,000 rows, 14 columns (no missing values)
* **Features (X):** `CreditScore`, `Geography`, `Gender`, `Age`, `Tenure`, `Balance`, `NumOfProducts`, `HasCrCard`, `IsActiveMember`, `EstimatedSalary`
* **Target (y):** `Exited` (`0`: Retained, `1`: Churned)

### Data Preprocessing
1. Dropped irrelevant columns (`RowNumber`, `CustomerId`, `Surname`).
2. Encoded categorical features (`Geography`, `Gender`) using `LabelEncoder` and `OneHotEncoder(drop='first')`, resulting in 11 input features.
3. Split the dataset into **75% training and 25% testing** (`random_state=60`).
4. Standardized feature values using `StandardScaler`.

### Model Architecture
Built using the Keras `Sequential` API:
* **Hidden Layer 1:** 4 units, `ReLU` activation (`input_dim=11`)
* **Hidden Layer 2:** 4 units, `ReLU` activation
* **Hidden Layer 3:** 4 units, `ReLU` activation
* **Output Layer:** 1 unit, `Sigmoid` activation
* **Total Parameters:** 93

### Training Configuration & Results
* **Optimizer:** Adam
* **Loss Function:** `binary_crossentropy`
* **Epochs:** 10
* **Batch Size:** 10
* **Training Accuracy (Epoch 10/10):** `83.19%` (`accuracy: 0.8319`, `loss: 0.4060`)

### Technologies Used
* Python
* NumPy & Pandas
* Scikit-learn
* TensorFlow / Keras
* Matplotlib & Seaborn
