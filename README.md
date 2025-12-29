# AETHERCLOUD NAWALA CHECKER API v1
[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/ALFARABs/API-NAWALA)

## BASE URL

```
https://apiv1.aethercloud.web.id
```

## REAL-TIME STATUS

Check the real-time status of the API.

**Endpoint:**
```http
GET /
```

**Response:**
```json
{
  "status": "online"
}
```

## CEK DOMAIN (REAL-TIME)

Check one or more domains against the Nawala blocklist in real-time.

**Endpoint:**
```http
GET /check?domain=DOMAIN
```

**Features:**
*   Check a single domain.
*   Check multiple domains (separated by commas).
*   Real-time checks.

---

### Contoh Request (Single Domain)

```http
GET /check?domain=google.com
```

### Contoh Request (Multiple Domains)

```http
GET /check?domain=google.com,pornhub.com,example.com
```

### Contoh Response

```json
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
```

---

## STATUS DOMAIN

| Status  | Keterangan (Description) |
| :------ | :----------------------- |
| `SAFE`    | Domain tidak diblokir (Domain is not blocked) |
| `BLOCKED` | Domain diblokir (Domain is blocked) |
| `UNKNOWN` | Status tidak terdeteksi (Status could not be determined) |
| `ERROR`   | Terjadi kesalahan (An error occurred) |

---

## CONTOH PAKAI CURL

### Single Domain

```sh
curl "https://apiv1.aethercloud.web.id/check?domain=google.com"
```

### Multiple Domains

```sh
curl "https://apiv1.aethercloud.web.id/check?domain=google.com,pornhub.com"
```

---

## CATATAN (Notes)

*   API is real-time.
*   No API key required.
*   Supports multi-domain checks.
*   Please use responsibly.
*   Ideal for bots, monitoring, and automation.

---

### AETHERCLOUD
Nawala Checker API v1
