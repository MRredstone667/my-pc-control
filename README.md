# 🖥️ PC Remote Control (ESP32-C3 & MQTT)

Tento projekt slouží jako jednoduchý, ale rychlý webový ovladač pro vzdálené zapínání a vypínání fyzického serveru pomocí mikrokontroleru **ESP32-C3** a MQTT brokera.

## 🚀 Jak to funguje?
Webová stránka je statická (GitHub Pages) a využívá technologii **WebSockets** přes knihovnu `mqtt.js`. Ke svému fungování vyžaduje specifický ověřovací token, který je předáván přímo v URL adrese. Bez tohoto tokenu nelze systém ovládat.

Po odeslání platného příkazu z webu:
1. Zpráva projde přes MQTT brokera (Shiftr.io).
2. ESP32-C3 přijme zprávu a sepne optočlen/relé připojené k základní desce PC na 3 sekundy.
3. ESP32 odešle potvrzovací zprávu přes webhook přímo do aplikace Discord.

## ⚠️ Upozornění pro návštěvníky (Invalidní token)
Pokud se po otevření webové stránky zobrazila chyba **"❌ Invalidní token!"**, znamená to, že jste na stránku přistoupili bez správných přihlašovacích údajů v URL adrese. 

Tento systém je privátní. Z bezpečnostních důvodů nejsou ověřovací tokeny veřejné.

## 🛠️ Použité technologie
* **Hardware:** ESP32-C3 Zero, Relé/Optočlen
* **Komunikace:** MQTT (Shiftr.io)
* **Frontend:** HTML, JavaScript (MQTT.js)
* **Notifikace:** Discord Webhooks
* **Hosting:** GitHub Pages
