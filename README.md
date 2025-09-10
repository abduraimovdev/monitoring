# 🚀 Docker Log Monitoring Stack (Grafana + Loki + Promtail)

Ushbu loyiha yordamida siz Docker konteynerlaringiz loglarini **Grafana** orqali kuzatishingiz mumkin.  
Loglarni yig‘ish uchun **Promtail**, saqlash uchun **Loki**, va vizualizatsiya uchun **Grafana** ishlatiladi.  

---

## 📂 Papka tuzilishi

monitoring/
├─ docker-compose.yml # Stack konfiguratsiyasi
├─ loki-config.yaml # Loki konfiguratsiyasi
└─ promtail-config.yaml # Promtail konfiguratsiyasi

yaml
Copy code

---

## ⚙️ O‘rnatish bosqichlari

1️⃣ **Papka yarating va fayllarni joylashtiring:**

mkdir monitoring && cd monitoring
2️⃣ Stackni ishga tushiring:

bash
Copy code
docker compose up -d
3️⃣ Ishlashini tekshiring:

bash
Copy code
docker ps
🌐 Xizmatlar
Grafana → http://localhost:3000
Default login:

pgsql
Copy code
User: admin
Password: admin
Loki → http://localhost:3100

Promtail → avtomatik ravishda Docker loglarini yig‘ib Loki’ga yuboradi.

📊 Grafana sozlash
Grafana’ga kiring (admin/admin bilan).

Configuration → Data Sources ga boring.

Loki data source qo‘shing:

URL: http://loki:3100

Save & Test bosing.

Explore bo‘limidan loglarni kuzatishingiz mumkin.

🔧 Foydali buyruqlar
Stackni ishga tushirish:

bash
Copy code
docker compose up -d
Loglarni real vaqtda ko‘rish:

bash
Copy code
docker compose logs -f
Stackni to‘xtatish:

bash
Copy code
docker compose down
📌 Eslatma
Agar serverda ishga tushirayotgan bo‘lsangiz, localhost o‘rniga server IP yoki domen ishlatishingiz kerak.

Grafana’da loglarni filtr qilish uchun container="app_nomi" kabi query yozishingiz mumkin.

Parollarni xavfsizlik uchun o‘zingizniki bilan almashtiring.

✅ Foydalanish maqsadi
Docker loglarini bir joyga to‘plash

Real-time monitoring qilish

Filtrlash va qidirish imkoniyati

Serverda muammo chiqqanda tezkor tahlil qilish

👨‍💻 Muallif: Abduraimovdev
