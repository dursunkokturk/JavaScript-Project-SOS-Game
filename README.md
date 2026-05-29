# TR
# SOS Oyunu (Tic-Tac-Toe)
İki oyunculu, tarayıcı tabanlı klasik X-O oyunu. Skorlar localStorage'a kaydedilir; sayfa yenilendiğinde bile puan tablosu korunur.

## Canlı Önizleme

[Proje Önizlemesi].(https://dursunkokturk.github.io/JavaScript-Project-SOS-Game/)


## Özellikler

- İki Oyunculu Mod — X ve O oyuncuları sırayla 3x3 ızgaraya tıklar
- Kazanma Tespiti — 8 olası kombinasyon kontrol edilir; kazanan alert ile duyurulur
- Beraberlik Tespiti — Tüm kareler dolduğunda ve kazanan yoksa beraberlik ilan edilir
- Skor Takibi — X, O ve beraberlik puanları ekranda anlık güncellenir
- localStorage Kalıcılığı — Skorlar tarayıcıya kaydedilir; sayfa yenilense de kaybolmaz
- Yeniden Oyna — Tahta temizlenir, sıra X'e döner; skorlar korunur
- Skorları Sil — Tüm puanlar sıfırlanır ve localStorage güncellenir
- Hover Animasyonları — Kare ve buton üzerine gelindiğinde ölçek ve renk efektleri


## Nasıl Oynanır?

- X oyuncusu boş bir kareye tıklar
- Sıra O oyuncusuna geçer
- Aynı hizada (yatay, dikey veya çapraz) üç aynı sembolü getiren oyuncu kazanır
- Tüm kareler dolup kazanan çıkmazsa oyun berabere biter
- Yeni oyun için Yeniden Oyna, skorları temizlemek için Skorları Sil butonuna basılır


## Teknolojiler

| Teknoloji  | Açıklama                                      |
| ---------- |-----------------------------------------------|
| HTML5      | Semantik sayfa yapısı                         |
| CSS3       | Grid, Flexbox, transition animasyonları       |
| JavaScript | Oyun mantığı, DOM manipülasyonu, localStorage |


### Proje Yapısı
sos-game/ <br>
├── index.html <br>
└── assets/ <br>
    ├── css/ <br>
    │   └── style.css <br>
    └── js/ <br>
        └── sos-game.js <br>

### Uygulama Akışı
Sayfa Açılır <br>
    │ <br>
    ▼ <br>
localStorage'da "sosScores" var mı? <br>
    │ <br>
    ├── Evet  → Skorlar localStorage'dan yüklenir <br>
    │ <br>
    └── Hayır → Skorlar 0 olarak ayarlanır ve localStorage'a yazılır <br>
                       │ <br>
                       ▼ <br>
               Oyun Başlar (currentPlayer = "X") <br>
                       │ <br>
                       ▼ <br>
               Kareye Tıklanır → X/O yazılır → Kazanan/Beraberlik kontrolü <br>
                       │ <br>
              ┌────────┴────────┐ <br>
           Kazanan            Beraberlik <br>
           Skoru artar        Beraberlik skoru artar <br>
           Oyun durur         Oyun durur <br>

## Kurulum
Proje herhangi bir bağımlılık gerektirmez.
bash# Repoyu klonlayın
git clone https://github.com/kullanici-adi/sos-game.git

### Proje klasörüne girin
cd sos-game

### index.html dosyasını tarayıcıda açın
open index.html

#### Not: sos-game.js dosyası defer ile yüklenir; DOM tamamen hazır olduktan sonra çalışır.


## Tasarım Detayları

- Renk Paleti:

    - #2563eb — Mavi (butonlar, X oyuncu rengi)
    - #ef4444 — Kırmızı (O oyuncu rengi)
    - #e5e7eb — Açık gri (kare arka planı)
    - #f3f4f6 — Çok açık gri (sayfa arka planı)
    - #1f2937 — Koyu (başlık metni)


- Font: system-ui, Arial, Helvetica
- Izgara: CSS Grid ile 3x3, her kare 100x100px
- Kart Efekti: Hover'da scale(1.05) ve translateY(-2px) animasyonları
