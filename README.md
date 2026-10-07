<p align="center">
  <img src="assets/logo.png" width="96" alt="LangChall ikonu" />
</p>

<h1 align="center">LangChall</h1>

<p align="center">
  Çeviri düelloları ve Türkiye haritasında fetih oyunuyla İngilizce öğreten bir mobil uygulama.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/durum-geliştirme%20aşamasında-orange" alt="Durum" />
  <img src="https://img.shields.io/badge/React%20Native-Expo%2057-000020?logo=expo" alt="Expo" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Node.js-Express-339933?logo=nodedotjs&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white" alt="PostgreSQL" />
</p>

> Uygulama geliştirme aşamasında ve henüz yayınlanmadı. Kaynak kodu private bir repoda duruyor. Bu repo projeyi tanıtmak için hazırlandı.

---

## Ekran görüntüleri

<p align="center">
  <img src="screenshots/conquest-map.jpg" width="820" alt="Bil ve Fethet haritası" />
  <br /><em>Bil ve Fethet: bota karşı Türkiye haritasında bölge fethi</em>
</p>

| Ana sayfa | Bil ve Fethet | Kapışma |
|:---:|:---:|:---:|
| <img src="screenshots/home.jpg" width="230" /> | <img src="screenshots/conquest-menu.jpg" width="230" /> | <img src="screenshots/battle.jpg" width="230" /> |

| Solo pratik | Kelime testi | Sözlük |
|:---:|:---:|:---:|
| <img src="screenshots/solo-levels.jpg" width="230" /> | <img src="screenshots/quiz.jpg" width="230" /> | <img src="screenshots/dictionary.jpg" width="230" /> |

| Lig tablosu | Profil | Giriş |
|:---:|:---:|:---:|
| <img src="screenshots/leaderboard.jpg" width="230" /> | <img src="screenshots/profile.jpg" width="230" /> | <img src="screenshots/login.jpg" width="230" /> |


## Oyun modları

### 🗺️ Bil ve Fethet
Türkiye haritasında bota ya da arkadaşına karşı oynanıyor. Kelime ve cümle sorularını doğru cevapladıkça bölge kazanıyorsun, rakibin üssünü alan oyunu kazanıyor.

### 🎯 Solo Pratik
A1'den C2'ye kadar bir seviye seçiyorsun ve süre dolmadan İngilizce bir paragrafı Türkçeye çeviriyorsun. Puan, çevirinin doğruluğuna ve kalan süreye göre hesaplanıyor.

### ⚔️ Kapışma
Aynı seviyedeki iki oyuncu aynı paragrafı çeviriyor (1, 3 ya da 5 tur). En iyi çeviriyi yapan turu alıyor.

### 🧠 Kelime Testi
Okurken bilmediğin bir kelimeye dokununca anlamı açılıyor ve kelimeyi sözlüğüne ekleyebiliyorsun. Kelime testi bu sözlükteki kelimelerden oluşuyor.

**Ayrıca:** arkadaş ekleme, liderlik tablosu, profil ve istatistikler, açık/koyu tema, e-posta ile şifre sıfırlama.

## Çeviriler nasıl puanlanıyor?

Bir cümlenin tek bir doğru çevirisi olmuyor. Kullanıcı eş anlamlı bir kelime kullanabilir ya da kelimelerin sırasını değiştirebilir. Sadece kelime eşleştirmesine bakılırsa doğru çeviriler de düşük puan alıyor. Bu yüzden puanlama iki kısımdan oluşuyor:

1. **Anlam benzerliği:** Kullanıcının çevirisi ve referans çeviri, çok dilli bir sentence-embedding modeliyle (`paraphrase-multilingual-MiniLM-L12-v2`) vektöre çevrilip karşılaştırılıyor. Model sunucuda yerel olarak çalışıyor, dışarıdaki bir API'ye bağlı değil.
2. **Kelime benzerliği:** Ortak kelime oranı ve Levenshtein mesafesi hesaplanıyor. Böylece cümlenin sadece yarısını çeviren biri, anlam benzerliği yüksek çıksa bile tam puan alamıyor.

Toplam puanın 80'i doğruluktan, 20'si kalan süreden geliyor. Embedding modeli bir sebeple çalışmazsa puanlama sadece kelime benzerliğiyle devam ediyor.

## Teknolojiler

| Katman | Kullanılanlar |
|---|---|
| Mobil | React Native (Expo), TypeScript, Expo Router, react-native-svg |
| Backend | Node.js, Express, TypeScript |
| Veritabanı | PostgreSQL (Supabase) |
| Kimlik doğrulama | JWT, bcrypt |
| Puanlama | Transformers.js ile sentence embedding |
| Veri hazırlama | Python script'leri |


**Sinem Aşkın** · [LinkedIn](https://www.linkedin.com/in/sinemaskinn) · [GitHub](https://github.com/asknnsinem)
