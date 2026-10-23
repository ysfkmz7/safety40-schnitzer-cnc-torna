<!-- pdf:skip-start -->
# SWOT Analizi — Schnitzer 2 Eksen CNC Ahşap Torna

**Bakış açısı:** Safety 4.0, yani siber güvenliğin emniyete etkisi ve CRA + Makine Tüzüğü 2023/1230 hazırlığı · **Dayanak:** Lab 1–4 çıktıları · 📄 [PDF](pdf/swot-analizi.pdf)

| Ad Soyad | Öğrenci No | Grup | Tarih |
|---|---|---|---|
| Yusuf Kaymaz | 230541084 | Gündüz-B | 23.10.2026 |
<!-- pdf:skip-end -->

> **Amaç:** Makineyi "iyi mi, kötü mü" diye değil, **20 Ocak 2027'de siber güvenlik CE'nin ön şartı olduğunda** nerede durduğuna göre değerlendirmek. İç faktörler (S, W) makinenin kendisinden, dış faktörler (O, T) mevzuat ve tehdit ortamından gelir. Her madde bir lab çıktısına bağlıdır.

## S · Güçlü yönler (iç)

- **Endüstriyel ve iyi belgelenmiş kontrol ekosistemi:** Siemens CNC (SINUMERIK 808D), Siemens servo sürücüler ve motorlar. Üreticinin güvenlik bültenleri ve yamaları takip edilebilir, bu da Lab 5'te SBOM ve CVE eşleştirmesini kolaylaştırır.
- **Emniyet bağımsızlığı için donanım altyapısı var:** sürücüler STO destekliyor (Lab 1, SF-1). Emniyeti CNC'den ayırmak sıfırdan tasarım gerektirmiyor.
- **Küçük ve sayılabilir saldırı yüzeyi:** 2 eksen, tek CNC, 3 dış bağlantı ve 28 kalemlik envanter (Lab 2). Tamamı yönetilebilir boyutta.
- **Tanınmış bileşenler:** FESTO pnömatik, PMI lineer sistem, Sick sensörler. Yedek parça ve dokümantasyon kolay bulunur.
- **Yerli üretici (Bursa) ve 24/7 destek:** teknik dosyaya, değişiklik taleplerine ve güvenli uzak destek kurulumuna ulaşmak kolay.

## W · Zayıf yönler (iç)

- **Kanıt eksikliği:** üretici sayfası emniyet donanımını (kapak kilidi, güvenlik rölesi) ve uzak erişim yöntemini belgelemiyor. Evidence Pack'te başlıkların çoğu "Yok" veya "Taslak" durumunda (VS-1 … VS-6).
- **Emniyet bağımsızlığı belirsiz:** kapak açma izni ve hız sınırı CNC'nin standart PLC'sinde olabilir (VS-3). Lab 3'te R-01 ve R-02'yi bu zayıflık yaratıyor.
- **Kontrolsüz program yolu:** USB ile her programın yüklenebilmesi ve G-kodu doğrulamasının olmaması (Lab 2, C4).
- **Hesap zayıflığı:** fabrika varsayılanı CNC parolaları ve paylaşılan hesaplar (H-1, H-2, K-1).
- **Üreticiye ait CAM yazılımı:** SBOM'u, güncelleme imzası ve destek süresi bilinmiyor (V-3, Lab 3'te R-03).

## O · Fırsatlar (dış)

- **Makine Tüzüğü 2023/1230 ile erken uyum:** Ek III 1.1.9 (bozulmaya karşı koruma) ve 1.2.1 (kontrol sistemlerinin dayanıklılığı) bugünden karşılanırsa, makine 2027'de CE'yi siber gerekliliklerle birlikte alır. Bu AB pazarı için zorunluluk, makinenin satıldığı diğer pazarlarda (İngiltere ve ABD bayileri) ise bir güven avantajıdır.
- **CRA ile süreç kurma:** SBOM, zafiyet yönetimi ve 24 sa / 72 sa / 14 gün bildirim zinciri üretici için bir "güvenli tasarım" referansına dönüşebilir.
- **Ucuz önlemlerle büyük etki:** uzak erişimi jump server + MFA arkasına alıp varsayılan kapalı yapmak R-01'i 27'den 6'ya indirir (Lab 3). Varsayılan parolaları değiştirmek R-02'nin L puanını 3'ten 1'e düşürür. Bunlar bütçe değil, disiplin ister.
- **Güvenli uzak destek bir hizmet olabilir:** jump server + VPN + MFA ile kurulan destek altyapısı (Lab 4), servis maliyetini düşürürken güveni artırır.

## T · Tehditler (dış)

- **Fırsatçı dış saldırganlar:** internete açılan uzak masaüstü araçları otomatik olarak taranır. Hedef seçilmez, bulunur (Lab 3, R-01 ve R-04).
- **Tedarik zinciri:** imzasız güncelleme veya servis dizüstüsü üzerinden değiştirilmiş PLC mantığı (R-03, S3 bayrağı).
- **Mevzuat yaptırımı:** 20 Ocak 2027'den sonra geçiş dönemi yok, siber gereklilikleri karşılamayan makine CE alamaz. CRA cezası 15 M€'ya veya cironun %2,5'ine kadar çıkabilir.
- **Kontrol ünitesinin yaşam döngüsü:** CNC veya sürücü üreticisinin desteği biterse yama gelmez ve L puanları zamanla yükselir.
- **İnsan faktörü:** "hat yavaş, hızı açayım" refleksi (R-02). Eğitim ve yetki ayrımı yoksa en iyi mimari bile delinir.

## SWOT matrisi — çıkan stratejiler

| | **Fırsatlar (O)** | **Tehditler (T)** |
|---|---|---|
| **Güçlü (S)** | **SO:** STO altyapısını kullanarak emniyeti CNC'den ayır, 2027 CE dosyasına "emniyet bağımsızlığı" kanıtı olarak koy | **ST:** Siemens güvenlik bültenlerini takip eden bir SBOM / yama süreci kur, kontrol ünitesinin yaşam döngüsü riskini erken gör |
| **Zayıf (W)** | **WO:** Ucuz önlemleri (parola, USB, varsayılan kapalı erişim) 30 gün içinde yap, varsayımları üreticiden doğrulat ve Evidence Pack'i "Taslak"tan "Var"a çek | **WT:** Kapak kilidi ve hız sınırı CNC'de kaldıkça R-01 / R-02 yaşar. Bu, en yüksek öncelikli tasarım değişikliğidir |

## Öncelikli 5 aksiyon

| # | Aksiyon | Kaynak | Etki |
|---|---|---|---|
| 1 | Uzak erişimi kapat, jump server + VPN + MFA ile yeniden aç | Lab 4, R-01 | 27 → 6 |
| 2 | CNC varsayılan parolalarını değiştir, erişim seviyelerini ayır | Lab 2, R-02 | L 3 → 1 |
| 3 | Kapak kilidi, hız sınırı ve punta kontrolünü bağımsız emniyet zincirine al (GR-1 … GR-4) | Lab 4, SF-2 / SF-3 / SF-4 | S 3 → 1 |
| 4 | USB portunu kilitle, programı 3D önizleme + kuru çalıştırma onayıyla üretime al | Lab 2, C4 | Kontrolsüz conduit kapanır |
| 5 | VS-1 … VS-6 varsayımlarını üreticiden yazılı olarak doğrulat, Evidence Pack'i güncelle | Makine Profili | Beyan → kayıt |

---

*SAFETY 4.0 BOOTCAMP · Schnitzer CNC Ahşap Torna Sürümü · Bu bir eğitim çıktısıdır, resmî denetim değildir.*
