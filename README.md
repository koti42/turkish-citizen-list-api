# PTT Address Data Scraper

A Laravel command to scrape address data (provinces, districts, neighborhoods) from PTT's postal code website.

## Features

- Scrapes all provinces, districts, and neighborhoods from PTT
- Saves data in JSON format
- Shows progress with colored console output
- Handles Turkish characters
- Cross-platform compatible (Windows/Linux)
- Rate limiting to prevent server overload
- Error handling and recovery
- Live progress tracking

## Requirements

- PHP >= 7.4
- Laravel >= 8.x
- Composer
- GuzzleHttp

## Installation

1. Install the required package:
```bash
composer require guzzlehttp/guzzle
```

2. Create the command:
```bash
php artisan make:command ScrapePttAddress
```

3. Copy the provided code to `app/Console/Commands/ScrapePttAddress.php`

## Usage

Run the command:
```bash
php artisan scrape:ptt-address
```

The script will:
1. Connect to PTT's website
2. Scrape all provinces
3. Get districts for each province
4. Get neighborhoods for each district
5. Save data to `storage/app/ptt_address_data.json`

## Output Format

```json
[
  {
    "il_id": "1",
    "il_adi": "ADANA",
    "ilceler": [
      {
        "ilce_id": "12",
        "ilce_adi": "ALADAG",
        "mahalleler": [
          {
            "mahalle_id": "1_2",
            "mahalle_adi": "AKOREN MAH",
            "posta_kodu": "01722"
          }
        ]
      }
    ]
  }
]
```

## Error Handling

- The script includes comprehensive error handling
- Recovers from connection issues
- Logs errors to console
- Saves progress regularly

---

# PTT Adres Veri Çekici

PTT'nin posta kodu web sitesinden adres verilerini (il, ilçe, mahalle) çeken Laravel komutu.

## Özellikler

- Tüm il, ilçe ve mahalleleri PTT'den çeker
- Verileri JSON formatında kaydeder
- Renkli konsol çıktısıyla ilerlemeyi gösterir
- Türkçe karakterleri düzgün işler
- Çoklu platform desteği (Windows/Linux)
- Sunucu yükünü önlemek için hız sınırlaması
- Hata yönetimi ve kurtarma
- Canlı ilerleme takibi

## Gereksinimler

- PHP >= 7.4
- Laravel >= 8.x
- Composer
- GuzzleHttp

## Kurulum

1. Gerekli paketi yükleyin:
```bash
composer require guzzlehttp/guzzle
```

2. Komutu oluşturun:
```bash
php artisan make:command ScrapePttAddress
```

3. Verilen kodu `app/Console/Commands/ScrapePttAddress.php` dosyasına kopyalayın

## Kullanım

Komutu çalıştırın:
```bash
php artisan scrape:ptt-address
```

Script şunları yapacak:
1. PTT web sitesine bağlanır
2. Tüm illeri çeker
3. Her il için ilçeleri alır
4. Her ilçe için mahalleleri alır
5. Verileri `storage/app/ptt_address_data.json` dosyasına kaydeder

## Çıktı Formatı

```json
[
  {
    "il_id": "1",
    "il_adi": "ADANA",
    "ilceler": [
      {
        "ilce_id": "12",
        "ilce_adi": "ALADAG",
        "mahalleler": [
          {
            "mahalle_id": "1_2",
            "mahalle_adi": "AKOREN MAH",
            "posta_kodu": "01722"
          }
        ]
      }
    ]
  }
]
```

## Hata Yönetimi

- Script kapsamlı hata yönetimi içerir
- Bağlantı sorunlarından kurtarır
- Hataları konsola loglar
- İlerlemeyi düzenli olarak kaydeder
