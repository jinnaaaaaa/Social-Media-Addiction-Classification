# Social Media Addiction Classification

โครงงานนี้เป็นการพัฒนาโมเดล Machine Learning เพื่อจำแนกระดับพฤติกรรมการเสพติดโซเชียลมีเดียของนักเรียนและนักศึกษา โดยใช้ข้อมูลเชิงพฤติกรรม และเทคนิคการเรียนรู้แบบมีผู้สอน (Supervised Learning) เพื่อช่วยวิเคราะห์และทำความเข้าใจปัจจัยที่ส่งผลต่อการใช้งานโซเชียลมีเดียอย่างไม่เหมาะสม


## ภาพรวมของโปรเจค (Project Overview)

- วิเคราะห์ข้อมูลพฤติกรรมการใช้โซเชียลมีเดียของนักเรียน/นักศึกษา
- เตรียมข้อมูลด้วยกระบวนการ Data Cleaning และ Feature Engineering
- จัดการปัญหา Class Imbalance ด้วยเทคนิค SMOTE
- สร้างและเปรียบเทียบโมเดล
  - K-Nearest Neighbors (KNN)
  - Gaussian Naive Bayes
- ประเมินประสิทธิภาพของโมเดลด้วย metrics มาตรฐาน


## ขั้นตอนการทำงาน (Workflow)

### 1. Exploratory Data Analysis (EDA)
- วิเคราะห์การกระจายของข้อมูล
- ตรวจสอบความสัมพันธ์ระหว่างตัวแปร
- ตรวจสอบ missing values และ outliers

### 2. Data Cleaning & Feature Engineering
- จัดการข้อมูลที่ขาดหาย
- แปลงข้อมูลเชิงหมวดหมู่ (Categorical Encoding)
- ปรับขนาดข้อมูลด้วย Feature Scaling

### 3. Model Training
- K-Nearest Neighbors (KNN)
- Gaussian Naive Bayes
- ใช้ **Pipeline ของ scikit-learn** เพื่อรวมขั้นตอน preprocessing และ modeling

### 4. Handling Imbalanced Data
- ใช้ **SMOTE** เพื่อปรับสมดุลของคลาสในชุดข้อมูลฝึก

### 5. Model Evaluation
- Accuracy
- Precision
- Recall
- F1-score


## วิธีการเรียนรู้ของโมเดล

- **ประเภทการเรียนรู้**: Supervised Learning  
- **ลักษณะงาน**: Binary Classification  
- **โมเดลที่ใช้**:
  - Gaussian Naive Bayes
  - K-Nearest Neighbors (KNN)



## Data Preprocessing

- แบ่งข้อมูล Train / Test = **80% / 20%**
- ใช้ **StandardScaler** สำหรับปรับขนาดข้อมูล
- รวมทุกขั้นตอนใน **Pipeline** เพื่อลดปัญหา Data Leakage
- ใช้ **SMOTE** เพื่อแก้ปัญหา Class Imbalance
- วิเคราะห์ **Multicollinearity** และลดจำนวน Feature เพื่อเพิ่มความเสถียรของโมเดล


## ผลการประเมินโมเดล (Model Performance)

### KNN (Reduced – 6 Features)
- **Accuracy**: 0.993  
- **F1-Score**: 0.995  
- **Recall**: 0.989  

### Gaussian Naive Bayes
- **Precision (Class ติดโซเชียล)**: 1.000  
- **F1-Score (Overall)**: 0.973  

โมเดล KNN หลังการลด Feature ให้ผลลัพธ์ดีที่สุดทั้งในด้านความแม่นยำ ความสมดุลของคลาส และความเสถียรของโมเดล
