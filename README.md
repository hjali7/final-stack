# Monitoring Stack with Prometheus, Grafana, and Loki

یک استک کامل مانیتورینگ که شامل Prometheus برای جمع‌آوری متریک‌ها، Grafana برای نمایش و داشبورد، و Loki برای مدیریت لاگ‌ها می‌باشد. این استک به صورت کامل با Docker و Docker Compose پیاده‌سازی شده است.

## 🚀 ویژگی‌ها

- **Prometheus**: جمع‌آوری و ذخیره‌سازی متریک‌ها
- **Grafana**: داشبورد و نمایش متریک‌ها و لاگ‌ها
- **Loki**: جمع‌آوری و مدیریت لاگ‌ها
- **Promtail**: جمع‌آوری لاگ‌ها از سیستم و ارسال به Loki
- **Docker Compose**: راه‌اندازی آسان و مدیریت سرویس‌ها
- **Volume Management**: ذخیره‌سازی پایدار داده‌ها
- **Network Isolation**: شبکه اختصاصی برای ارتباط بین سرویس‌ها

## 📋 پیش‌نیازها

- Docker
- Docker Compose
- حداقل 4GB RAM
- حداقل 20GB فضای دیسک

## 🛠️ نصب و راه‌اندازی

1. کلون کردن مخزن:
```bash
git clone [آدرس مخزن]
cd [نام پوشه]
```

2. اجرای استک:
```bash
docker-compose up -d
```

## 🔌 پورت‌های پیش‌فرض

- Grafana: `http://localhost:3000`
- Prometheus: `http://localhost:9090`
- Loki: `http://localhost:3100`

## 📁 ساختار پروژه

```
.
├── docker-compose.yml
├── prometheus/
│   └── prometheus.yml
├── grafana/
│   └── provisioning/
├── loki/
│   └── loki-config.yaml
└── promtail/
    └── promtail-config.yaml
```

## ⚙️ تنظیمات

### Prometheus
- فایل کانفیگ: `prometheus/prometheus.yml`
- داده‌ها در volume `prometheus_data` ذخیره می‌شوند

### Grafana
- داشبوردها و تنظیمات در `grafana/provisioning`
- داده‌ها در volume `grafana_data` ذخیره می‌شوند

### Loki
- فایل کانفیگ: `loki/loki-config.yaml`
- داده‌ها در volume `loki_data` ذخیره می‌شوند

### Promtail
- فایل کانفیگ: `promtail/promtail-config.yaml`
- لاگ‌های سیستم را از `/var/log` جمع‌آوری می‌کند

## 🔄 مدیریت سرویس‌ها

- شروع مجدد همه سرویس‌ها:
```bash
docker-compose restart
```

- مشاهده لاگ‌ها:
```bash
docker-compose logs -f
```

- توقف سرویس‌ها:
```bash
docker-compose down
```

## 🔒 امنیت

- تمام سرویس‌ها در یک شبکه Docker اختصاصی اجرا می‌شوند
- پورت‌های ضروری به صورت انتخابی در معرض دید قرار گرفته‌اند
- داده‌ها در volume‌های Docker ذخیره می‌شوند

## 📈 مانیتورینگ

- **Prometheus**: جمع‌آوری متریک‌های سیستم و سرویس‌ها
- **Grafana**: داشبوردهای پیش‌فرض برای نمایش متریک‌ها
- **Loki**: جمع‌آوری و جستجوی لاگ‌ها
- **Promtail**: جمع‌آوری لاگ‌های سیستم

## 🤝 مشارکت

از مشارکت شما در بهبود این پروژه استقبال می‌کنیم. لطفاً:

1. یک issue برای مشکل یا پیشنهاد خود ایجاد کنید
2. یک branch جدید برای تغییرات خود بسازید
3. تغییرات خود را commit کنید
4. یک pull request ایجاد کنید

## 📝 لایسنس

این پروژه تحت لایسنس MIT منتشر شده است. برای اطلاعات بیشتر به فایل [LICENSE](LICENSE) مراجعه کنید. 