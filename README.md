# Metaframer Test Panosu

bench-0022 (Metaframer v16 Apps) üzerindeki 8 test sitesi ve kurulu Frappe uygulamalarının doğrudan açılış adresleri.

**Canlı pano:** https://metafrappe.github.io/metaframer-test-panosu/

## Nasıl kullanılır

1. Panoda siteyi seç (üstteki sekmeler) veya uygulama adı yaz.
2. Sitenin **giriş** bağlantısından oturum aç (erp-test: demo@demo.com, diğerleri: test@test.com).
3. Uygulama satırındaki adrese tıkla, açıldığını gör, kutuyu işaretle. İşaretler tarayıcında saklanır.

Etiketler: **hazır** kurulumla açılır · **ön koşul** sitede kayıt açmak gerekir (POS Profile, Wiki Space, Çalışan) · **dış servis** API anahtarı veya ayrı sunucu ister (Stalwart, SFU, Meta, Twilio, S3, LLM).

## Siteler

| Site | Sektör | Kurulum |
|---|---|---|
| erp-test | Ticaret, e-ticaret, dağıtım | tamam |
| klinik-test | Sağlık | tamam |
| restoran-test | Restoran, kafe (URY) | tamam, test@test.com kullanıcısı açılıyor |
| perakende-test | Mağaza, e-ticaret | tamam |
| egitim-test | Okul, kurs, kantin POS | tamam, POS Profili "Kantin" hazır |
| finans-test | Leasing, faktoring, AB e-fatura | kontrol edilecek |
| lojistik-test | Forwarder, nakliye | tamam |
| bt-ajans-test | BT hizmet, platform ve AI | kontrol edilecek |

## Bilinen durumlar

- **WhatsApp Integration** yalnız bench 000018'e taşınan klinik-test ve restoran-test'te kurulu; Meta Integration bench'ten çıkarıldı (modül adı çakışması).
- **Mail** ve **Frappe Suite Mail** Stalwart posta sunucusu ister; **Meet** ve **Suite Meet** mediasoup SFU ister. İkisi de henüz kurulmadı.
- **Customer** kaydında Payment Terms Template zorunlu (bir uygulamanın Property Setter'ı). Müşteri açmadan önce bir şablon oluştur; egitim-test'te "Peşin" var.
- Türkiye hesap planı şablonunda uç hesap az; POS için satış, maliyet ve silme hesapları elle açıldı (egitim-test).

Adresler `index.html` içindeki `SITES` dizisinde tutulur; grup eşlemesi `GROUP_OF` sözlüğünde. Yeni site veya uygulama için o diziye satır ekle.
