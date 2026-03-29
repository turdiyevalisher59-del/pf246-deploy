# PF-246 O'rganish Tizimi

O'zbekiston Respublikasi Markaziy banki — AYOQSH tekshiruv savolnomasi tizimi.

## Tezkor deploy (3 qadam)

### 1-qadam: GitHub-ga yuklash
```bash
cd pf246-deploy
git init
git add .
git commit -m "PF-246 tizimi"
git remote add origin https://github.com/SIZNING_USERNAME/pf246-survey.git
git branch -M main
git push -u origin main
```

### 2-qadam: Vercel-ga ulash
1. https://vercel.com saytiga GitHub akkauntingiz bilan kiring
2. "Add New Project" tugmasini bosing
3. `pf246-survey` reponi tanlang
4. Framework: "Other" tanlang
5. "Deploy" tugmasini bosing

### 3-qadam: Tayyor!
Vercel sizga `https://pf246-survey.vercel.app` kabi havola beradi. Shu havola orqali tizimga kirasiz.


## Login ma'lumotlari

### Admin
Login: `admin` | Parol: `Admin@2025`

### Tekshiruvchilar (22 ta)

| № | Login | Parol | Vakil | Hudud | Telefon |
|---|-------|-------|-------|-------|---------|
| 1 | user01 | User01@2025 | O'.Matboboyev | Angren sh. | 77-777-28-44 |
| 2 | user02 | User02@2025 | S.Sobirov | Bekobod sh. | 97-711-12-27 |
| 3 | user03 | User03@2025 | B.Xakimov | Nurafshon sh. | 90-134-30-34 |
| 4 | user04 | User04@2025 | M.Abduraxmonov | Olmaliq sh. | 93-511-64-10 |
| 5 | user05 | User05@2025 | X.Maxammadiyev | Ohangaron sh. | 95-982-46-64 |
| 6 | user06 | User06@2025 | X.Abduvaliyev | Chirchiq sh. | 97-445-12-35 |
| 7 | user07 | User07@2025 | S.Abbosov, M.Xaitov | Yangiyo'l sh. | 94-681-57-40 |
| 8 | user08 | User08@2025 | A.Otaxonov | Bekobod t. | 93-585-22-20 |
| 9 | user09 | User09@2025 | R.Alayev | Bo'ka t. | 99-400-04-68 |
| 10 | user10 | User10@2025 | U.Azimberdiyev | Bo'stonliq t. | 90-808-55-80 |
| 11 | user11 | User11@2025 | F.Bekmurodov | Zangiota t. | 97-782-59-79 |
| 12 | user12 | User12@2025 | M.Umarov | Qibray t. | 99-001-02-30 |
| 13 | user13 | User13@2025 | A.Yarmatov | Quiyichirchiq t. | 98-128-86-89 |
| 14 | user14 | User14@2025 | J.Davronbekov | Oqqo'rg'on t. | 77-777-01-81 |
| 15 | user15 | User15@2025 | Sh.Axrorov | Ohangaron t. | 93-524-80-75 |
| 16 | user16 | User16@2025 | K.Xusomiddinov | Parkent t. | 94-622-76-67 |
| 17 | user17 | User17@2025 | A.Yo'ldoshxonov | Piskent t. | 90-324-67-89 |
| 18 | user18 | User18@2025 | A.Karimov | Toshkent t. | 97-744-40-12 |
| 19 | user19 | User19@2025 | M.Yusupov | O'rtachirchiq t. | 97-704-39-53 |
| 20 | user20 | User20@2025 | N.Tursunov | Chinoz t. | 97-922-70-00 |
| 21 | user21 | User21@2025 | A.Shomirov | Yuqorichirchiq t. | 94-945-16-64 |
| 22 | user22 | User22@2025 | A.Mansurov | Yangiyo'l t. | 97-720-73-37 |

Admin sozlamalari orqali vakillar ismi, hududi va telefon raqamini o'zgartirish mumkin.


## Tizim imkoniyatlari

### Tekshiruvchilar uchun
- 26 ta savol, 9 ta bo'lim (barchasi admin tomonidan sozlanadi)
- Ha/Yo'q, matnli, sonli, tanlash, terminal holati turdagi savollar
- Har bir bo'limga rasm va video dalillar biriktirish (faqat kameradan, galeriyadan emas)
- GPS lokatsiya avtomatik aniqlanadi va har 30 soniyada ping yuboriladi
- Haqiqiy manzil Nominatim (OpenStreetMap) reverse geocoding orqali aniqlanadi
- Ma'lumotnomani yuborishdan oldin ko'rib chiqish (review) modali
- PDF formatda yuklash (yuborishdan oldin va keyin)
- Yuborish tarixi lokatsiya va joy nomi bilan
- Parol o'zgartirish

### Admin uchun
- Umumiy statistika va hududlar bo'yicha kartochkalar
- Kartochkani bosib vakilning barcha ma'lumotlarini ko'rish
- Foydalanuvchilar jadvali (ism, hudud, telefon, holat)
- Barcha ma'lumotnomalar jadvali (o'chirish imkoni bilan)
- Jonli xarita (Leaflet/OpenStreetMap) — real-time user lokatsiyalari
- Lokatsiya pinglar ro'yxati (hudud, ko'cha, joy nomi bilan)
- Eksport: PDF hisobot, Telegram, Email, JSON, CSV, Clipboard
- **Sozlamalar paneli**: tizim nomi, bo'limlar, savollar, vakillar — hammasini o'zgartirish

### PF-246 Disclaimer
- Prezident Farmoni vazifalari kartochka sifatida (bosib ochish/yopish)
- 3 ta bo'lim: bank xodimlari, rahbarlar, Markaziy bank mas'ullari vazifalari


## Texnik ma'lumot

Bu loyiha bitta standalone HTML fayldan iborat. Barcha CSS, JavaScript, savollar va foydalanuvchi ma'lumotlari bitta `index.html` ichida. Tashqi kutubxonalar CDN orqali yuklanadi:
- Google Fonts (Plus Jakarta Sans)
- jsPDF + AutoTable (PDF generatsiya)
- Leaflet (Jonli xarita)
- Nominatim API (Reverse geocoding)

Ma'lumotlar brauzerning localStorage'ida saqlanadi. Har bir foydalanuvchining sozlamalari va yuborishlari shu brauzerda qoladi.


## Muhim eslatma

Hozirgi versiyada barcha ma'lumotlar localStorage'da saqlanadi (client-side). Bu shuni anglatadiki, har bir foydalanuvchi faqat o'z brauzeridan yuborgan ma'lumotlarni ko'radi. Haqiqiy real-time sinxronizatsiya uchun backend (Supabase, Firebase va h.k.) qo'shish tavsiya etiladi.
