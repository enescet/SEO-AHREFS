# Visual Dashboard — SEO Ahrefs Skill

Bu dosya, SEO verilerini görsel olarak sunmak için kullanılacak artifact yapısını açıklar.

## Ne Zaman Dashboard Göster?

- Kullanıcı "göster", "tablo", "dashboard", "görsel" derse
- 5+ keyword verisi varsa (otomatik olarak öner)
- Rakip analizi yapıldıysa

## Dashboard Bölümleri

### 1. Keyword Tablosu
Sütunlar: Keyword | Aylık Hacim | KD (0-100) | CPC | Trend | Öneri

KD Renk Kodu:
- 0-29 → Yeşil (Kolay)
- 30-59 → Sarı (Orta)  
- 60-79 → Turuncu (Zor)
- 80-100 → Kırmızı (Çok Zor)

### 2. Quick Win Vurgusu
Volume > 500 VE KD < 30 olan keywordleri öne çıkar

### 3. Rakip Karşılaştırma Tablosu
Sütunlar: Site | DR | Backlinks | Tahmini Traffic | Fırsat

### 4. Title Önizleme & Karakter Sayacı
- Google SERP önizlemesi (mavi link + açıklama formatında)
- Anlık karakter sayacı (50-60 arası yeşil, dışarısı kırmızı)
- "Kopyala" butonu

### 5. Meta Description Önizleme
- 150-160 karakter aralığı göstergesi

## Artifact Teknolojisi

React JSX kullan. Tailwind CSS class'larıyla stil ver.
Import: useState, recharts (ScatterChart, BarChart için)

## Renk Paleti
- Primary: #0f62fe (mavi)
- Success: #24a148 (yeşil)  
- Warning: #f1c21b (sarı)
- Danger: #da1e28 (kırmızı)
- Background: #f4f4f4
- Card bg: #ffffff

## Örnek Artifact Başlangıcı

```jsx
import { useState } from "react";

const SEODashboard = ({ keywords, competitors, titles }) => {
  const [activeTab, setActiveTab] = useState("keywords");
  
  const getKDColor = (kd) => {
    if (kd < 30) return "bg-green-100 text-green-800";
    if (kd < 60) return "bg-yellow-100 text-yellow-800";
    if (kd < 80) return "bg-orange-100 text-orange-800";
    return "bg-red-100 text-red-800";
  };

  // ... tablo ve tab yapısı
};

export default SEODashboard;
```
