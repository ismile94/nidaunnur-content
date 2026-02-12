# Nida Ünnür – Uzaktan İçerik

Bu klasör GitHub'a yüklenip [https://github.com/ismile94/nidaunnur-content](https://github.com/ismile94/nidaunnur-content) reposunda yayınlanır. Uygulama içeriği JSDelivr CDN üzerinden çeker.

## Yapı

- `manifest.json` – Tüm resimlerin listesi (dil, tarih aralığı, URL)
- `images/ramadan/` – Ramazan ayına özel görseller
- `images/kandil/` – Kandil gecelerine özel görseller

## manifest.json formatı

```json
{
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

## GitHub'a yükleme

1. `nidaunnur-content` klasörünün **içeriğini** `ismile94/nidaunnur-content` reposuna push edin
2. Kök dizinde `manifest.json` ve `images/` olsun
3. JSDelivr CDN birkaç dakika içinde güncel içeriği sunar
