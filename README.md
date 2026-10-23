# Safety 4.0 Bootcamp — Schnitzer 2 Eksen CNC Ahşap Torna

Safety 4.0 Readiness Bootcamp laboratuvar föylerinin **kendi seçtiğimiz makineye** uyarlanmış hâli. Her laboratuvar bu repoya ayrı bir commit olarak eklenir. Föyler hem **Markdown** (GitHub'da doğrudan okunur) hem **PDF** (yazdırılabilir föy) olarak bulunur.

| Ad Soyad | Öğrenci No | Grup |
|---|---|---|
| Yusuf Kaymaz | 230541084 | Gündüz-B |

## Makine

**Schnitzer 2 Eksen 2 Ünite CNC Ahşap Torna** (Kestel / Bursa). Siemens CNC (SINUMERIK 808D) · 4 kW iş mili, 5.000–6.000 dev/dk · X/Z servo eksenler · FESTO pnömatik merkezleme ve punta · V-bıçak + çanak bıçak · USB + Ethernet · üretici tarafından uzaktan destek.

Teknik özellikler, kaynaklar ve doğrulanacak varsayımlar: **[00-makine-profili.md](00-makine-profili.md)**

## İlerleme

| Hafta | Laboratuvar | Çıktı | Evidence Pack | Durum | Föy |
|---|---|---|---|---|---|
| 1 | Lab 1 · Safety Architecture | Safety Function Map | EP 03 | ✅ Tamamlandı | [Markdown](lab1-safety-architecture.md) · [PDF](pdf/lab1-safety-architecture.pdf) |
| 2 | Lab 2 · IEC 62443 Mini Workshop | Zone / Conduit Diagram | EP 01 · EP 05 | ⏳ Sırada | — |
| 3 | Lab 3 · Threat & Risk + Risk Matrix | Risk Register | EP 04 | ⏳ Sırada | — |
| 4 | Lab 4 · Secure Remote Access | Secure Architecture | EP 02 · EP 06 | ⏳ Sırada | — |
| 1–4 | SWOT Analizi | Stratejik değerlendirme | — | ⏳ Sırada | — |
| 5 | Lab 5 · SBOM / CVE / Patch | Vulnerability Decision | EP 08 – EP 11 | ⏳ Sırada | — |
| 6 | Lab 6 · CRA Incident Simulation | Incident Workflow | EP 13 | ⏳ Sırada | — |
| 7 | Lab 7 · AI Safety Challenge | AI Fail-Safe Decision | — | ⏳ Sırada | — |

## Föylerdeki işaretler

| İşaret | Anlamı |
|---|---|
| `UYARLANDI` | Orijinal föy sorusu bu makineye göre değiştirildi |
| `EK SORU` | Makineye özgü, kendi eklediğimiz soru |
| VS-1 … VS-6 | Sahada / üreticiden doğrulanacak varsayımlar ([Makine Profili](00-makine-profili.md)) |
| SF-1 … SF-4 | Emniyet fonksiyonları (Lab 1) |
| D / Y / H / K / B / V | Envanter kalemleri: donanım, yazılım, hesap, anahtar, dış bağlantı, veri akışı (Lab 2) |
| Z0 … Z5 · C1 … C6 | Zone'lar ve conduit'ler (Lab 2) |
| R-01 … R-04 | Risk Register senaryoları (Lab 3) |
| GR-1 … GR-5 | Emniyet bağımsızlığı gereksinimleri (Lab 4) |

## Evidence Pack durumu

| # | Başlık | Durum | Kaynak |
|---|---|---|---|
| 01 | Asset Inventory | Yok | Lab 2 |
| 02 | Network Architecture | Yok | Lab 4 |
| 03 | Safety Functions | Taslak | Lab 1 — SF-1 … SF-4 |
| 04 | Cyber Risk Assessment | Yok | Lab 3 |
| 05 | Zone & Conduit | Yok | Lab 2 |
| 06 | Remote Access Procedure | Yok | Lab 2 + Lab 4 |
| 07 | User/Role Matrix | Yok | — |
| 08 | Software/Firmware Inv. | Yok | Lab 2 + Lab 5 |
| 09 | SBOM | Yok | Lab 5 |
| 10 | Vulnerability Records | Yok | Lab 5 |
| 11 | Patch/Update Records | Yok | Lab 5 |
| 12 | Backup & Restore | Yok | — |
| 13 | Incident Response | Yok | Lab 6 |
| 14 | Change Management | Yok | — |
| 15 | Verification/Test | Yok | — |

Durumlar kanıt hiyerarşisini izler: **Yok → Taslak → Var → Doğrulanmış.**

## Repo yapısı

```text
├── README.md                        ← bu sayfa, ilerleme tablosu
├── 00-makine-profili.md             ← makine, kaynaklar, varsayımlar
├── lab1-safety-architecture.md
├── lab2-iec62443-zone-conduit.md
├── lab3-threat-risk-matrix.md
├── lab4-secure-remote-access.md
├── swot-analizi.md
└── pdf/                             ← föy tasarımında PDF'ler
```

## Kaynaklar

- [Schnitzer — 2 Axis 2 Units ürün sayfası](https://schnitzer.com.tr/en/machine/2-axes-2-units.html)
- [Schnitzer — CNC Wood Turning Machines](https://schnitzer.com.tr/en/)
- [Scott+Sargeant — Schnitzer 2 axis CNC Woodworkers Lathe](https://www.scosarg.com/schnitzer-2-axis-cnc-woodworkers-lathe)
- [Surplus Record — Schnitzer 2 Axis CNC Wood Lathe (SINUMERIK 808D)](https://surplusrecord.com/listing/schnitzer-2-axis-cnc-controlled-wood-lathe-39-4-max-length-3-94-min-length-6-46-max-square-2022-346819/)
- [Control Engineering — SINUMERIK 808D Advanced](https://www.controleng.com/ec-sinumerik-808d-advanced/)
- Safety 4.0 Bootcamp ders sunumu, Lab 3 ders notu, laboratuvar föyleri ve Kavramlar Sözlüğü

---

*Bu repo bir eğitim çıktısıdır; resmî denetim, uygunluk değerlendirmesi veya belgelendirme değildir ve CE/mevzuat uygunluğu garantisi vermez.*
