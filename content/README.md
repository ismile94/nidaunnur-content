# Nida – uzaktan güncellenen içerik

Bu klasördeki dosyaları Nida (Flutter) uygulaması doğrudan GitHub'dan okur.
Buradaki bir düzeltme **uygulama güncellemesi gerekmeden** kullanıcılara ulaşır.

| Dosya | İçerik |
|---|---|
| `duas.json` | Dualar (14 dil) |
| `hadiths.json` | Hadisler (14 dil) |
| `esmaulhusna.json` | Esmaül Hüsna: anlam ve kullanım (14 dil) |
| `gunun_ayeti/gunun_ayeti_<dil>.json` | Günün ayeti, Hicri takvimin 355 günü |

> Kökteki eski `duas.json` / `hadiths.json` bu klasörden bağımsızdır; uygulama onları okumaz.

## Değişiklik ne zaman görünür?

- Uygulama her dosyayı en çok **6 saatte bir** kontrol eder (değişmediyse yeniden indirmez).
- GitHub'ın kendi önbelleği ~5 dakikadır.
- Yeni metin, kart bir sonraki açılışta yeniden yüklendiğinde görünür.

Yani bir düzeltme genelde birkaç saat içinde, en geç ~6 saatte kullanıcılara ulaşır.

## Düzenleme kuralları

Yalnızca **metinleri** değiştirin:

- dua / hadis: `text` (hadiste `source` de olabilir)
- esma: `meaning`, `usage`
- günün ayeti: `ayet.metin_<dil>`

`id`'leri, alan adlarını, sayıları ve listelerin uzunluğunu değiştirmeyin.

### Bozuk düzenleme uygulamayı bozmaz

Uygulama indirdiği dosyayı kullanmadan önce kontrol eder. Şu durumlarda dosyayı yok sayar ve elindeki son sağlam içerikle devam eder:

- JSON bozuksa (ör. eksik virgül),
- bir alan eksikse ya da tipi yanlışsa (ör. sayı yerine metin),
- Esma listesi 99 değilse,
- takvimde bir ay eksikse.

Hata düzelince bir sonraki kontrolde yeni dosya alınır.

### Dil ekleme ve çıkarma

- Dua/hadis/esma dosyasında bir dil eksikse, o dil için uygulamanın gömülü kopyası kullanılır.
- Yeni dil kodu eklemek yalnızca uygulama da o dili destekliyorsa işe yarar.

## Uygulama reposuyla eşitleme (nida-flutter)

Uygulamadan buraya kopyalamak için:

```
python tools/sync_nidaunnur_content.py
```

Buradaki düzeltmeleri bir sonraki sürüme gömmek için (`--pull`), ardından bundle'ı yeniden üretin:

```
python tools/sync_nidaunnur_content.py --pull
python tools/embed_l10n_bundles.py
```
