<div align="center">
  <img src="https://via.placeholder.com/150/1e293b/10b981?text=ST" alt="Şefim Temiz Logo" width="120" />
  <h1>👨‍🍳 Şefim Temiz</h1>
  <p><b>Yapay Zeka Destekli Gerçek Zamanlı Kişisel Koruyucu Donanım (PPE) Tespit Sistemi</b></p>

  <p>
    <img alt="Python" src="https://img.shields.io/badge/Python-3.10-3776AB?style=flat-square&logo=python&logoColor=white" />
    <img alt="YOLOv8" src="https://img.shields.io/badge/YOLOv8-Ultralytics-00ffff?style=flat-square&logo=ultralytics&logoColor=black" />
    <img alt="OpenCV" src="https://img.shields.io/badge/OpenCV-Computer%20Vision-5C3EE8?style=flat-square&logo=opencv&logoColor=white" />
    <img alt="NVIDIA" src="https://img.shields.io/badge/CUDA-NVIDIA_RTX_4060-76B900?style=flat-square&logo=nvidia&logoColor=white" />
  </p>
</div>

---

## 📖 Proje Özeti
**Şefim Temiz**, endüstriyel mutfaklarda, laboratuvarlarda ve temiz üretim alanlarında **Kişisel Koruyucu Donanım (PPE)** kullanımını otonom hale getiren yapay zeka tabanlı bir görüntü işleme projesidir. Sistem, derin öğrenme algoritmaları aracılığıyla çalışanların üzerindeki ekipmanları kameralardan canlı olarak saniyeler içinde analiz eder. Amacımız, iş sağlığı ve güvenliği süreçlerini tamamen otomatikleştirerek insan hatasını minimuma indirmektir.

---

## 🎯 Tespit Edilen Donanımlar (Sınıflar)
Model, sistem kameralarından alınan görüntüler üzerinden şu 4 temel sınıfı otomatik olarak algılar:
- 🟢 **Bone** (Saç filesi / Koruyucu Tane)
- 🟢 **Maske** (Ağız ve Burun Koruyucu)
- 🟢 **Eldiven** (Hijyenik / Koruyucu Eldiven)
- 🟢 **Kolluk** (Bilek ve Kol Koruyucu)

*(Eksik veya hatalı kullanım durumlarında sistem anlık olarak tespit yapabilmektedir.)*

---

## 🧮 Model ve Donanım Altyapısı
* **Algoritma:** YOLOv8 (Ultralytics) — Son teknoloji, yüksek hızlı ve hassas nesne algılama (Object Detection) mimarisi.
* **Donanım Optimizasyonu:** Model, yüksek frame (FPS) değerleriyle, gecikmesiz gerçek zamanlı analiz yapabilmesi için doğrudan **NVIDIA RTX 4060 GPU** üzerinde CUDA çekirdekleri ile donanımsal olarak hızlandırılmış ve optimize edilmiştir.
* **Geliştirme Ortamı:** Python, PyTorch.

---

## 📌 Proje Kapsamı ve Veri Hattı (Data Pipeline)

### 1️⃣ Veri Toplama ve Hazırlama
Başarılı bir yapay zeka modelinin temelini oluşturan veri kümemiz titizlikle oluşturulmuştur:
* **Veri Toplama:** Çeşitli senaryolarda ve farklı ortam ışıklarında çekilmiş, PPE içeren binlerce çalışma ortamı görüntüsünün senkronize derlenmesi.
* **Etiketleme (Annotation):** Her bir görüntünün *Bounding Box (Sınırlayıcı Kutu)* yöntemiyle 4 temel sınıf için manuel olarak etiketlenmesi.
* **Veri Ön İşleme (Preprocessing):** Kameralardan gelen görüntü boyutlarındaki tutarsızlığı gidermek için *Resize* (Yeniden Boyutlandırma) ve *Auto-Orient* (Otomatik Yönlendirme) işlemleri.
* **Veri Artırma (Data Augmentation):** Modelin ezberlemesini (overfitting) engellemek ve her ortama (farklı ışık, yön, kamera açısı) uyum sağlaması için uygulanan sentetik veri artırma teknikleri:
  * *Flip* (Yatay / Dikey Çevirme)
  * *Rotation* (Çevirme / Döndürme)
  * *Brightness & Contrast* (Parlaklık ve Kontrast manipülasyonu)
  * *Noise* injection (Gürültü ekleme)

---

## 🚀 Kurulum ve Kullanım
*(Kişisel ortamınızda çalıştırmak için model ağırlık (`.pt`) dosyaları ve `requirements.txt` bağımlılıklarını kurduğunuzdan emin olun.)*

```bash
# Gerekli kütüphanelerin yüklenmesi
pip install -r requirements.txt

# Gerçek zamanlı (webcam/kamera) algılamayı başlatmak için
python main.py --source 0 --weights runs/detect/train/weights/best.pt
```

---

<div align="center">
  <p><i>"Sıfır İhlal, Maksimum Hijyen ve Güvenlik"</i></p>
</div>
