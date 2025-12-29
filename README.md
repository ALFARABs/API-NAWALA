# AETHERCLOUD NAWALA CHECKER API v1
================================

# BASE URL
--------
https://apiv1.aethercloud.web.id


# REAL-TIME STATUS
----------------
GET /

Response:
{
  "status": "online"
}


# CEK DOMAIN (REAL-TIME)
---------------------
GET /check?domain=DOMAIN

• Bisa 1 domain
• Bisa banyak domain (pisahkan dengan koma)
• Real-time check


Contoh Request (Single):
GET /check?domain=google.com


Contoh Request (Multiple):
GET /check?domain=google.com,pornhub.com,example.com


Contoh Response:
{
  "client_ip": "103.xxx.xxx.xxx",
  "latency_ms": 1823,
  "count": 3,
  "timestamp": "2025-12-29T14:10:22+08:00",
  "results": [
    {
      "domain": "google.com",
      "status": "SAFE"
    },
    {
      "domain": "pornhub.com",
      "status": "BLOCKED"
    },
    {
      "domain": "example.com",
      "status": "SAFE"
    }
  ]
}


STATUS DOMAIN
-------------
SAFE     : Domain tidak diblokir  
BLOCKED  : Domain diblokir  
UNKNOWN  : Status tidak terdeteksi  
ERROR    : Terjadi kesalahan  



CONTOH PAKAI CURL
-----------------
curl "https://apiv1.aethercloud.web.id/check?domain=google.com"

curl "https://apiv1.aethercloud.web.id/check?domain=google.com,pornhub.com"


# CATATAN
-------
• API real-time
• Tidak perlu API key
• Mendukung multi-domain
• Gunakan secara wajar
• Cocok untuk bot, monitoring, dan automation


AETHERCLOUD
-----------
Nawala Checker API v1

