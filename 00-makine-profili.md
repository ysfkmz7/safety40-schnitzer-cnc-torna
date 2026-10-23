# Makine Profili — Schnitzer 2 Eksen 2 Ünite CNC Ahşap Torna

| Ad Soyad | Öğrenci No | Grup | Tarih |
|---|---|---|---|
| Yusuf Kaymaz | 230541084 | Gündüz-B | 23.10.2026 |

Bu dosya, Lab 1–7 boyunca üzerinde çalışılan makinenin **tek kaynak** profilidir. Tüm föylerdeki varlıklar, kapılar ve varsayımlar buradaki bilgilere dayanır.

## Makine nedir, ne yapar?

Kare kesitli ahşap kütüğü iki eksende CNC ile tornalayarak mobilya ayağı, korkuluk babası, merdiven dikmesi, sap gibi simetrik parçalar üreten bir makinedir. İş parçası pnömatik olarak merkezlenir ve punta ile sıkılır, iş mili parçayı yüksek hızda döndürür, bıçak taşıyıcı iki eksende hareket ederek V-bıçak ve çanak bıçakla kesim yapar.

- **Üretici:** Schnitzer (SchnitzerCNC), Kestel / Bursa, Türkiye
- **Model:** 2 Eksen 2 Ünite (2 Axis 2 Units) CNC ahşap torna
- **Seçim kaynağı:** AİMSAD – twm.com.tr üretici listesi (ders kapsamında)

## Teknik özellikler

| Özellik | Değer | Kaynak |
|---|---|---|
| Kontrol ünitesi | Siemens CNC (bayi ilanlarına göre **SINUMERIK 808D**) | Üretici sayfası + bayi ilanı |
| Eksen motorları | Siemens servo — X: 0,75 kW · Z: 1 kW | Üretici sayfası |
| İş mili motoru | 4 kW asenkron (Siemens) | Bayi ilanı |
| İş mili hızı | 5.000–6.000 dev/dk (ilanlarda iki farklı değer var) | Bayi ilanları |
| Toplam çalışma gücü | 6 kW | Üretici sayfası |
| Maks. kesit / çap | 160 × 160 mm · Ø230 mm | Üretici sayfası |
| İş parçası boyu | 20–1000 mm | Üretici sayfası |
| Eksen hızları | Uzun eksen 75 m/dk · kısa eksen 15 m/dk | Üretici sayfası |
| Kesici üniteler | V-bıçak (üçgen) + çanak (kupa) bıçak | Üretici sayfası |
| İş parçası bağlama | FESTO pnömatik merkezleme + pnömatik punta sıkma | Üretici sayfası + bayi ilanı |
| Kumanda elemanları | El çarkı + ayak pedalı | Bayi ilanı |
| Hareket / yağlama | PMI lineer kızak · otomatik yağlama | Üretici sayfası |
| Sensörler | Sick sensörler (≤ 6 mm algılama — konum/referans) | Üretici sayfası |
| Yazılım | Üreticinin kendi yazılımı: 2D çizimden G-koduna, 3D önizleme | Üretici sayfası |
| Kontrol arayüzleri | USB portu · RJ45 Ethernet (808D Advanced) · sürücülerde STO desteği | Siemens 808D Advanced duyurusu |
| Ağırlık / boyut | 1.600 kg · 3088 × 1293 × 1838 mm | Üretici sayfası |
| Destek | 24/7 teknik destek | Üretici sayfası |

## Varsayımlar (sahada / üreticiden doğrulanacak)

Üretici sayfası emniyet donanımını ve uzak erişim yöntemini belgelemiyor. Ders yönteminde "envanterde olmayan kapıdan senaryo yazılmaz" kuralı var, bu yüzden eksik bilgileri **açıkça işaretlenmiş varsayımlar** olarak envantere ekledik. Her varsayım Evidence Pack'te "Taslak" durumundadır.

| ID | Varsayım | Kullanıldığı yer |
|---|---|---|
| VS-1 | Kesim bölgesi koruyucu kapakla kapalı ve kapak kilitli. Kilidin iş milinin durmasına bağlı olup olmadığı bilinmiyor. | Lab 1, Lab 3 |
| VS-2 | E-stop zinciri bir güvenlik rölesi üzerinden sürücülerin STO girişine ve ana kontaktöre gidiyor. | Lab 1, Lab 2 |
| VS-3 | Kapak açma izni ve iş milinin azami hız sınırı, CNC'nin standart (emniyet sınıfı olmayan) PLC'sinde ve makine parametrelerinde. | Lab 1, Lab 3, Lab 4 |
| VS-4 | Üretici uzaktan destek için CAM PC'ye uzak masaüstü yazılımı kurmuş. PC hem fabrika ağına (internet) hem Ethernet ile CNC'ye bağlı. | Lab 2, Lab 3, Lab 4 |
| VS-5 | Programlar CAM PC'den USB bellek veya Ethernet ile CNC'ye aktarılıyor. | Lab 2, Lab 3 |
| VS-6 | CNC erişim seviyesi parolaları (üretici / servis / kullanıcı) fabrika varsayılanı olarak bırakılmış olabilir. | Lab 2, Lab 3 |

> VS-3, VS-4 ve VS-6 bilinçli olarak **kötü durum** varsayımlarıdır. Lab 4'teki "MEVCUT" tablo bu duruma göre çizildi. Sahada daha iyi bir durum görülürse riskler yeniden puanlanır.

## Mevzuat bağlamı

| Düzenleme | Tarih | Bu makine için anlamı |
|---|---|---|
| Makine Tüzüğü (AB) 2023/1230 | 20 Ocak 2027, geçiş dönemi yok | Ek III 1.1.9: bozulmaya karşı koruma ve müdahale kanıtı. Ek III 1.2.1: kontrol sistemleri kötü niyetli girişimlere dayanıklı olmalı. Siber güvenlik CE'nin ön şartı. |
| CRA (AB) 2024/2847 | Bildirim yükümlülüğü 11 Eylül 2026 · tam uygulama 11 Aralık 2027 | Makine USB, Ethernet ve yazılım içerdiği için "dijital unsurlu ürün". SBOM, zafiyet yönetimi, destek süresi ve 24 sa / 72 sa / 14 gün bildirim zinciri. |

## Kaynaklar

- [Schnitzer — 2 Axis 2 Units ürün sayfası](https://schnitzer.com.tr/en/machine/2-axes-2-units.html)
- [Schnitzer — CNC Wood Turning Machines (üretici ana sayfası)](https://schnitzer.com.tr/en/)
- [Scott+Sargeant — Schnitzer 2 axis CNC Woodworkers Lathe](https://www.scosarg.com/schnitzer-2-axis-cnc-woodworkers-lathe)
- [Surplus Record — Schnitzer 2 Axis CNC Wood Lathe (SINUMERIK 808D)](https://surplusrecord.com/listing/schnitzer-2-axis-cnc-controlled-wood-lathe-39-4-max-length-3-94-min-length-6-46-max-square-2022-346819/)
- [Surplus Record — Schnitzer 2 Axis 3 Unit (Siemens 808D)](https://surplusrecord.com/listing/schnitzer-2-axis-3-unit-cnc-controlled-wood-lathe-39-4-max-length-6-3-square-5-4-hp-5000-rpm-siemens-808d-control-2026-new-1109229/)
- [Control Engineering — SINUMERIK 808D Advanced (USB, Ethernet, STO)](https://www.controleng.com/ec-sinumerik-808d-advanced/)
- Safety 4.0 Bootcamp ders sunumu, Lab 3 ders notu ve Kavramlar Sözlüğü
