
# SSH/VPN API Services

## Access

Melihat Port dan API Key

    cat /etc/gegevps/api/.env

Output

    APIKEY='db9f7734-9dab-44e2-89f9-xxxxxxxxxxxx'
    LISTEN_PORT=3000

API Key : `db9f7734-9dab-44e2-89f9-xxxxxxxxxxxx`

API Port : `3000`

## Endpoint

Format

    http://[IP_SERVER]:[API_PORT]/[PATH]

Contoh :

    http://123.123.123.123:3000/ssh

## Create

Method : `POST`

|Tunnel|Path|APIKey|user|pass|expi|core|
|--|--|--|--|--|--|--|
|SSH/OpenVPN|/ssh|✅|✅|✅|✅|⛔️|
|SoftetherVPN|/sevpn|✅|✅|✅|✅|⛔️|
|VMess|/vmess|✅|✅|⛔️|✅|✅|
|VLess|/vless|✅|✅|⛔️|✅|✅|
|Trojan|/trojan|✅|✅|⛔️|✅|✅|
|Shadowsocks|/shadowsocks|✅|✅|⛔️|✅|✅|
|Socks5|/socks5|✅|✅|⛔️|✅|✅|
|Trojan-Go|/trojango|✅|✅|⛔️|✅|⛔️|
|Hysteria|/hysteria|✅|✅|⛔️|✅|⛔️|
|UDP Custom|/udpcustom|✅|✅|⛔️|✅|⛔️|

Contoh penggunaan menggunakan cURL (Linux Command)

    curl -sS -kL -X POST "http://123.123.123.123:3000/ssh" \
        -H "APIKey: db9f7734-9dab-44e2-89f9-xxxxxxxxxxxx" \
        -d "core=xray" \
        -d "user=gegeuserapi" \
        -d "pass=gegeuserapi" \
        -d "expi=30"

**Catatan**
✅ - Diperlukan
⛔️ - Tidak digunakan

## Delete

Method : `DELETE`

|Tunnel|Path|APIKey|user|core|
|--|--|--|--|--|
|SSH/OpenVPN|/ssh|✅|✅|⛔️|
|SoftetherVPN|/sevpn|✅|✅|⛔️|
|VMess|/vmess|✅|✅|✅|
|VLess|/vless|✅|✅|✅|
|Trojan|/trojan|✅|✅|✅|
|Shadowsocks|/shadowsocks|✅|✅|✅|
|Socks5|/socks5|✅|✅|✅|
|Trojan-Go|/trojango|✅|✅|⛔️|
|Hysteria|/hysteria|✅|✅|⛔️|
|UDP Custom|/udpcustom|✅|✅|⛔️|

Contoh penggunaan menggunakan cURL (Linux Command)

    curl -sS -kL -X DELETE "http://123.123.123.123:3000/ssh" \
        -H "APIKey: db9f7734-9dab-44e2-89f9-xxxxxxxxxxxx" \
        -d "core=xray" \
        -d "user=gegeuserapi"

**Catatan**
✅ - Diperlukan
⛔️ - Tidak digunakan

## Response

Success

    {
    	"ok": true,
    	...
    }

Failed

    {
    	"ok": false,
    	"description": "Error Message"
    }
