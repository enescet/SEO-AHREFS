---
name: seo-ahrefs
description: |
  Ahrefs MCP entegrasyonuyla güçlü SEO analizi, keyword araştırması, rakip analizi ve SEO uyumlu içerik üretimi yapar. 
  Kullanıcı bir konu, ürün, URL veya keyword girdiğinde bu skill'i MUTLAKA kullan. Title yazarken, meta description üretirken, blog içeriği oluştururken, ürün açıklaması yazarken, rakip siteler analiz ederken, backlink profili incelerken hepsinde bu skill devreye girmeli. 
  "SEO", "keyword", "title yaz", "meta", "rakip analizi", "ahrefs", "arama hacmi", "sıralama", "içerik yaz" gibi ifadeler geçtiğinde — hatta kullanıcı sadece "bu ürün için içerik yaz" dese bile — bu skill'i kullan. Visual artifact içinde dashboard olarak da sunulabilir.
---

# SEO Ahrefs Skill

Bu skill, Ahrefs MCP ile entegre çalışarak gerçek zamanlı SEO verisi çeker ve bunu kullanarak SEO uyumlu içerik üretir, rakip analizi yapar, keyword stratejisi oluşturur.

---

## 🔧 Gereksinimler

- **Ahrefs MCP** bağlı olmalı (`https://api.ahrefs.com/mcp/mcp`)
- Claude.ai'da Ahrefs connector aktif olmalı

---

## 📋 Workflow — Adım Adım

### ADIM 1: Kullanıcı Niyetini Anla

Kullanıcının ne istediğini belirle:

| Niyet | Ne Yapacaksın |
|-------|---------------|
| Title / Meta yazmak | → ADIM 2 → ADIM 4 → Keyword'lü title üret |
| Blog / Ürün içeriği | → ADIM 2 → ADIM 3 → ADIM 5 → İçerik yaz |
| Rakip analizi | → ADIM 2 → ADIM 3 → ADIM 6 |
| Keyword araştırması | → ADIM 2 → ADIM 3 → Dashboard göster |
| Backlink analizi | → ADIM 7 |

---

### ADIM 2: Ana Keyword'ü Belirle

Eğer kullanıcı açıkça belirtmediyse, konuyu/ürünü/URL'yi analiz ederek 1 ana keyword + 3-5 alternatif keyword öner ve kullanıcıya sor. Doğrudan devam etmek istiyorsa, en mantıklı keyword'ü kendin seç ve devam et.

---

### ADIM 3: Ahrefs'ten Keyword Verisi Çek

Ahrefs MCP üzerinden şu sırayla tool çağrıları yap:

```
1. keyword_search veya keywords_explorer_overview
   → Search volume, keyword difficulty (KD), CPC, global volume

2. keyword_suggestions veya related_terms  
   → LSI keywords, long-tail variations, related searches

3. serp_overview (varsa)
   → Kim sıralanıyor? İlk 10 sonuç
```

**Çekilen verilerden şunu çıkar:**
- 🎯 Ana keyword: search volume + KD
- 📊 En az 10 ilgili keyword (volume + KD ile birlikte)
- 🏆 İlk 3 rakip URL
- 💡 "Quick win" keywordler (yüksek volume, düşük KD)

---

### ADIM 4: SEO Uyumlu Title & Meta Üret

Ahrefs verisini kullandıktan sonra şu kurallara göre yaz:

#### Title Yazma Kuralları
- **50-60 karakter** arasında tut
- Ana keyword **başa yakın** koy (ilk 3 kelime içinde ideal)
- Rakiplerden farklılaş — sadece keyword doldurma yapma
- İçinde **rakamlar** veya **güçlü kelimeler** kullan (En İyi, 2024, Ücretsiz, Nasıl, vb.)
- En az **3 farklı title alternatifi** sun

#### Meta Description Kuralları
- **150-160 karakter** arasında
- Ana keyword + 1-2 LSI keyword içermeli
- CTA (call to action) ile bitir
- Her title için ayrı meta yaz

#### Örnek Çıktı Formatı:
```
📌 TITLE SEÇENEKLERİ
━━━━━━━━━━━━━━━━━━
1. [Ana Keyword] — [Fayda/Özellik] | [Marka] (58 karakter)
   🔑 Kullanılan keywords: [keyword1], [keyword2]
   
2. [Sayı] + [Ana Keyword]: [Fayda] (54 karakter)
   🔑 Kullanılan keywords: [keyword1], [keyword3]

3. [Soru formatı: Nasıl/En iyi vb.] [Ana Keyword]? (52 karakter)
   🔑 Kullanılan keywords: [keyword2], [keyword4]

📝 META DESCRIPTIONS
━━━━━━━━━━━━━━━━━━
1. için: [150-160 karakter meta, keyword'lü, CTA'lı]
2. için: [...]
3. için: [...]
```

---

### ADIM 5: SEO Uyumlu İçerik Üret

Keyword verisine göre içerik yaz. Şu yapıyı kullan:

#### İçerik Yapısı
```
H1: [Ana keyword içeren başlık]

Giriş paragrafı (100-150 kelime):
- İlk cümlede ana keyword geçmeli
- LSI keyword'leri doğal olarak serpiştir
- Okuyucunun sorununu tanımla

H2: [İlgili keyword içeren alt başlık]
[İçerik bloğu — 200-300 kelime]

H2: [Başka ilgili keyword]
[İçerik bloğu]

... (kullanıcının istediği uzunluğa göre)

Sonuç + CTA
```

#### İçerik İçinde Keyword Kullanımı
- **Keyword density**: %1-2 arası (zorlamadan)
- Her H2'de en az 1 LSI keyword
- İlk ve son paragrafta ana keyword
- Alt taglar, bold metinler için ilgili keywordler

---

### ADIM 6: Rakip Analizi

SERP'ten çekilen rakip URL'leri için:

```
Ahrefs MCP → site_overview veya domain_overview
→ Her rakip için: DR (Domain Rating), backlink sayısı, 
  organic traffic tahmini, top keywords
```

#### Rakip Analizi Çıktı Formatı:
```
🏆 RAKIP ANALİZİ — "[keyword]" için
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
#1 rakip.com
   DR: 72 | Backlinks: 4,200 | Organic Traffic: ~45K/ay
   Güçlü yönleri: [...]
   Zayıf yönleri / Fırsatlar: [...]

#2 rakip2.com  
   ...

💡 STRATEJİK FIRSAT:
   [Bu keyword'de nasıl rakiplerden öne geçilir]
```

---

### ADIM 7: Backlink Analizi

```
Ahrefs MCP → backlinks veya referring_domains
→ Bir URL veya domain için backlink profili
```

---

## 📊 Visual Dashboard (İsteğe Bağlı)

Kullanıcı "göster", "dashboard", "görsel" veya "tablo" derse — ya da çok fazla keyword verisi varsa — bunu React/HTML artifact içinde göster:

Artifact içinde şunları göster:
- Keyword tablosu (volume, KD, CPC sütunları, renkli KD göstergesi)
- Quick win vs. hard keywords ayrımı (scatter plot veya renkli liste)
- Rakip karşılaştırma tablosu
- Title karakter sayacı (anlık)
- Seçilen title/meta'yı kopyala butonu

Detaylar için → `references/visual-dashboard.md` dosyasına bak

---

## 🚨 Önemli Kurallar

1. **Ahrefs verisi olmadan title/meta yazma** — Önce veriyi çek, sonra yaz
2. **Her zaman birden fazla seçenek sun** — Minimum 3 title, 3 meta
3. **Kaynak göster** — "Ahrefs verisi: X keyword, Hacim: Y, KD: Z" şeklinde
4. **Karakter sayısını belirt** — Her title/meta için yanına karakter sayısı ekle
5. **Türkçe içerik için** — Türkçe keyword varyasyonlarına dikkat et (çoğul, ekler)
6. **E-ticaret ürünleri için** — Ürün kategorisi + özellik + fiyat/fırsat kombinasyonu kullan

---

## 📁 Referans Dosyalar

- `references/visual-dashboard.md` — Dashboard artifact kodu ve tasarım rehberi
- `references/title-formulas.md` — 20+ kanıtlanmış title formülü
- `references/keyword-scoring.md` — Quick win keyword belirleme kriterleri
