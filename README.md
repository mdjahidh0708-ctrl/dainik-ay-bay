# দৈনিক আয় ব্যয় — v1.2 SQLite + Backup/Restore

ফিচার:
- SQLite local database
- আয়/ব্যয় স্থায়ীভাবে সংরক্ষণ
- Transaction delete
- Report
- JSON Backup
- JSON Restore
- Restore confirmation

চালাতে:
flutter pub get
flutter run

APK:
flutter build apk

Backup: Settings → Backup
Restore: Settings → Restore

Restore করলে বর্তমান local transactions replace হয়ে backup-এর data বসবে।


## v1.3 নতুন ফিচার
- CSV Export: Settings থেকে সব লেনদেন CSV ফাইলে export করা যাবে।
- Wallet Management: Cash/Bank/bKash/Nagad/Rocket সহ custom wallet যোগ/মুছে ফেলা যাবে।
- Custom Category: আয় ও ব্যয়ের আলাদা custom category যোগ/মুছে ফেলা যাবে।
- SQLite database version upgraded to 2 with wallets and categories tables.

### Build
```bash
flutter pub get
flutter analyze
flutter build apk
```


## Codemagic দিয়ে APK Build
এই project-এ `codemagic.yaml` দেওয়া আছে। GitHub repository-তে project push করে Codemagic-এ repository connect করুন এবং `android-release` workflow চালু করুন। Build সফল হলে Artifacts থেকে APK download করা যাবে।

Build steps:
1. `flutter pub get`
2. `flutter analyze`
3. `flutter build apk --release`

নোট: এই workflow unsigned release APK তৈরি করবে। Google Play Store-এ প্রকাশ করতে Android signing/keystore configuration আলাদাভাবে সেট করতে হবে।
