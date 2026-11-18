# 🪙 Kerala Gold Rate API (Free & Real-Time)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![API Status](https://img.shields.io/badge/API-Online%20%26%20Live-brightgreen)](https://ponn.in/kerala_gold_rate_today.json)
[![Edge Caching](https://img.shields.io/badge/CDN-Cloudflare%20Edge-orange)](https://ponn.in/)
[![CORS: Enabled](https://img.shields.io/badge/CORS-Enabled%20(*)-blue)](https://ponn.in/kerala_gold_rate_today.json)

A completely free, reliable, and real-time **Kerala Gold Rate JSON API**.

Unlike traditional financial APIs that charge monthly subscriptions or require API keys, this endpoint provides:
- **No API Keys**
- **No Sign-ups**
- **No Rate Limits**
- **CORS Enabled** (`Access-Control-Allow-Origin: *`)
- **Global Low Latency** (Served directly from Cloudflare Pages edge CDN)

Official website: **[ponn.in](https://ponn.in/)**

---

## 🚀 Live Endpoint

```http
GET https://ponn.in/kerala_gold_rate_today.json
```

- **JSON Schema**: [`https://ponn.in/kerala_gold_rate_today.schema.json`](https://ponn.in/kerala_gold_rate_today.schema.json)
- **Cache-Control**: 60 seconds (`public, max-age=60, must-revalidate`)

---

## 📦 Sample JSON Response

```json
{
  "updated_at": "2026-11-18T04:01:52Z",
  "date": "2026-11-18",
  "rates": {
    "k22": {
      "purity": "22K (916)",
      "per_gram": 12215,
      "per_pavan": 97720
    },
    "k24": {
      "purity": "24K (Pure)",
      "per_gram": 13609,
      "per_pavan": 108872
    },
    "k18": {
      "purity": "18K",
      "per_gram": 10000,
      "per_pavan": 80000
    }
  },
  "consensus": {
    "engines_audited": 6,
    "status": "healthy"
  },
  "source": "https://ponn.in/"
}
```

---

## 💻 Quick Integration Examples

### 1. cURL
```bash
curl -s https://ponn.in/kerala_gold_rate_today.json | jq
```

### 2. JavaScript / Node.js / Browser (Fetch)
```javascript
async function getGoldRate() {
  const res = await fetch('https://ponn.in/kerala_gold_rate_today.json');
  const data = await res.json();
  
  console.log(`22K (1g): ₹${data.rates.k22.per_gram}`);
  console.log(`22K (1 Pavan): ₹${data.rates.k22.per_pavan}`);
}

getGoldRate();
```

### 3. Python (`requests`)
```python
import requests

res = requests.get('https://ponn.in/kerala_gold_rate_today.json')
data = res.json()

k22_gram = data['rates']['k22']['per_gram']
k22_pavan = data['rates']['k22']['per_pavan']

print(f"Today's 22K Gold Rate: ₹{k22_gram}/g (₹{k22_pavan}/pavan)")
```

### 4. Flutter / Dart
```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> fetchGoldRate() async {
  final url = Uri.parse('https://ponn.in/kerala_gold_rate_today.json');
  final response = await http.get(url);

  if (response.statusCode == 200) {
    final data = jsonDecode(response.body);
    print("22K Gram: ₹${data['rates']['k22']['per_gram']}");
    print("22K Pavan: ₹${data['rates']['k22']['per_pavan']}");
  }
}
```

### 5. PHP
```php
<?php
$json = file_get_contents('https://ponn.in/kerala_gold_rate_today.json');
$data = json_decode($json, true);

echo "22K Rate: ₹" . $data['rates']['k22']['per_pavan'] . " / Pavan";
?>
```

---

## 🛡️ License

This project and its public endpoint are licensed under the [MIT License](LICENSE). Free for both personal and commercial use.
