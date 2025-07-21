# Bookify - تطبيق تأجير الكتب

## مقدمة عن المشروع
تطبيق **Bookify** هو تطبيق عبر منصات (Cross-Platform) تم تطويره باستخدام Flutter، يهدف إلى تسهيل عملية تأجير الكتب بين المستخدمين والمكتبات. يضم التطبيق نوعين من المستخدمين:
- **المستخدم العادي (User):** يمكنه تصفح الكتب واستئجارها.
- **المدير (Admin):** يمكنه إدارة الكتب، والمستخدمين، والطلبات.

## أهداف المشروع
- توفير منصة سهلة لتصفح واستئجار الكتب.
- تسهيل إدارة عمليات التأجير للمسؤولين.
- دعم تجربة مستخدم جذابة وسلسة عبر Flutter.
- تأمين الوصول عبر نظام مصادقة موثوق.

## المتطلبات الوظيفية

### واجهات المستخدم (User Features)
- تسجيل الدخول / التسجيل.
- تصفح الكتب حسب التصنيف أو البحث.
- عرض تفاصيل الكتاب (اسم، مؤلف، صورة، وصف...).
- إمكانية تأجير كتاب.
- صفحة “طلباتي” لعرض حالة الطلبات (قيد الانتظار، تمت الموافقة، مرفوضة).

### واجهات المدير (Admin Features)
- تسجيل دخول خاص بالمدير.
- لوحة تحكم.
- إضافة / تعديل / حذف الكتب.
- عرض وإدارة الطلبات الواردة من المستخدمين.
- قبول / رفض طلبات الإيجار.

## الهيكلية العامة للتطبيق (Architecture)
- **Frontend:** Flutter (بنية نظيفة مع استخدام `Riverpod` أو `Bloc`)
- **Backend:** Firebase Firestore و Firebase Authentication
- **State Management:** Riverpod أو Bloc حسب تفضيل الفريق
- **Routing:** GoRouter أو Flutter Navigator 2.0
- **Storage:** Firebase Cloud Storage للصور
- **API Integration:** Firebase SDK
- **Persistence:** SharedPreferences أو Riverpod Persistence لتخزين الجلسة

## هيكلة المشروع (Project Structure)
│
├── main.dart               # نقطة البداية للتطبيق
├── app.dart                # تعريف التطبيق و Theme
│
├── models/                 # نماذج البيانات (Book, User, Order)
│   ├── book.dart
│   ├── user.dart
│   └── order.dart
│
├── services/               # خدمات مثل Firebase API، المصادقة، قواعد البيانات
│   ├── auth_service.dart
│   ├── book_service.dart
│   └── order_service.dart
│
├── providers/              # Riverpod providers أو blocs لإدارة الحالة
│   ├── auth_provider.dart
│   ├── book_provider.dart
│   └── order_provider.dart
│
├── views/                  # شاشات التطبيق (UI)
│   ├── user/               # شاشات المستخدم العادي
│   │   ├── home_screen.dart
│   │   ├── book_detail_screen.dart
│   │   └── my_rentals_screen.dart
│   │
│   └── admin/              # شاشات المدير
│       ├── admin_dashboard.dart
│       ├── manage_books_screen.dart
│       └── manage_orders_screen.dart
│
└── widgets/                # ويدجتات مشتركة (buttons, cards, loaders)
    ├── book_card.dart
    ├── custom_button.dart
    └── loading_indicator.dart

## شاشات التطبيق (UI Screens)

### للمستخدم:
- Splash Screen  
- Login/Register  
- Home (قائمة الكتب)  
- Book Details  
- Booking Page  
- My Rentals  

### للمدير:
- Admin Login  
- Admin Dashboard  
- Add/Edit Book  
- Orders Management  

## المصادقة وإدارة الجلسات
- المصادقة تعتمد على Firebase Authentication.
- يتم التحقق من الدور (مستخدم أو مدير) بعد تسجيل الدخول.
- تخزين بيانات الجلسة محليًا باستخدام `SharedPreferences`.

## التقنيات والأدوات المستخدمة

| المجال         | الأداة أو التقنية        |
|----------------|------------------------|
| اللغة          | Dart                   |
| الإطار         | Flutter                |
| إدارة الحالة   | Riverpod أو Bloc       |
| المصادقة       | Firebase Authentication|
| قاعدة البيانات | Firebase Firestore     |
| التخزين        | Firebase Storage       |
| الرفع والنشر   | Firebase Hosting / Play Store |

## ميزات إضافية
- دعم الترجمة (عربي/إنجليزي) باستخدام `flutter_localizations`.
- دعم الوضع الليلي والنهاري.
- إشعارات عند قبول أو رفض الطلب باستخدام `Firebase Messaging`.

## خطوات التطوير (Workflow)
1. إعداد المشروع وتهيئة Firebase.
2. بناء الواجهات الأساسية (Splash - Login - Home).
3. إعداد Firebase Auth.
4. إعداد قاعدة البيانات والموديلات.
5. ربط الواجهات بالبيانات باستخدام Riverpod.
6. اختبار تدفق تأجير الكتب.
7. بناء لوحة تحكم المدير.
8. اختبار شامل للتطبيق.
9. رفع التطبيق وتجهيزه للنشر.

## النتائج المتوقعة
- تطبيق عملي كامل يدعم تسجيل الدخول والتصفح والتأجير.
- واجهة مخصصة للمدير لإدارة النظام.
- أداء عالي وتجربة مستخدم ممتازة.
- إمكانية توسيع التطبيق لاحقًا بإضافة الدفع أو الدردشة.
