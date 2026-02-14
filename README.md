# Nida Ünnür – Uzaktan İçerik

Bu klasör GitHub'a yüklenip [https://github.com/ismile94/nidaunnur-content](https://github.com/ismile94/nidaunnur-content) reposunda yayınlanır. Uygulama içeriği JSDelivr CDN üzerinden çeker.

## Yapı

- `manifest.json` – Tüm resimlerin listesi (dil, tarih aralığı, URL)
- `images/ramadan/` – Ramazan ayına özel görseller
- `images/kandil/` – Kandil gecelerine özel görseller

## manifest.json formatı

```json
{
  "localizedTextByType": {
    "ramadan": {
      "tr": {
        "shareText": "Ramazan Mubarek",
        "quoteText": "Ramazan rahmet, magfiret ve bereket ayidir."
      },
      "en": {
        "shareText": "Blessed Ramadan",
        "quoteText": "Ramadan is the month of mercy, forgiveness, and blessings."
      }
    }
  },
  "specialDays": [
    {
      "id": "ramadan-start",
      "type": "ramadan",
      "startDate": "2026-02-19",
      "endDate": "2026-02-22",
      "locales": {
        "tr": {
          "shareText": "Ramazana Hos Geldin",
          "quoteText": "Niyetini tazele..."
        },
        "en": {
          "shareText": "Welcome Ramadan",
          "quoteText": "Renew your intention..."
        }
      }
    }
  ],
  "items": [
    {
      "id": "ramadan-1",
      "imageUrl": "images/ramadan/dosya.png",
      "lang": "tr",
      "startDate": "2025-02-12",
      "endDate": "2026-04-15",
      "type": "ramadan",
      "shareText": "Ramazan Mübarek"
    }
  ]
}
```

- `lang`: tr, en, ar, pt, es, de, nl
- `startDate` / `endDate`: YYYY-MM-DD, içerik bu aralıkta gösterilir
- `shareText`: Paylaşımda kullanılacak metin
- `localizedTextByType`: Tipe göre çok dilli paylaşım ve resim üstü yazı metinleri
- `quoteText`: Resim üstüne yazılan metin (uygulama diliyle gelir)
- `specialDays`: Belirli tarih aralığına özel içerik metinleri (dua/hadis/tavsiye/ibadet)
- `specialDays[].locales`: Dil bazlı metinler; uygulama önce kullanıcı dilini, sonra `en` ve `tr` fallback'ini dener
- Son 10 gün için öneri: genel hazırlık, 27. geceye bir gun kala hatirlatma ve 27. gece metni gibi daha spesifik bloklar ekleyin

## GitHub'a yükleme

1. `nidaunnur-content` klasörünün **içeriğini** `ismile94/nidaunnur-content` reposuna push edin
2. Kök dizinde `manifest.json` ve `images/` olsun
3. JSDelivr CDN birkaç dakika içinde güncel içeriği sunar
