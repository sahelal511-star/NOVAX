#index.html
نموذج PredıcGuard بلغة بايثون
# ===== نموذج أبشر مع PredictGuard (نسخة مطوّرة) =====

# قائمة لتخزين الأنشطة
activities = []

# عداد الأنشطة المشبوهة
suspicious_count = 0

print("مرحباً بك في نموذج PredictGuard التجريبي!\n")

# نطلب من المستخدم إدخال 3 أنشطة كمثال
for i in range(3):
    activity = input(f"ادخلي النشاط رقم {i+1}: ")
    activities.append(activity)

    # التحقق من نوع النشاط
    if activity.lower() in ["خطر", "login from new device", "suspicious transaction"]:
        print("🔔 PredictGuard: نشاط غير طبيعي!")
        suspicious_count += 1
    elif activity.lower() in ["password change", "update info"]:
        print("⚠️ PredictGuard: تغيير بيانات مهمة")
    else:
        print("✅ PredictGuard: كل شيء طبيعي")

# ملخص بعد إدخال الأنشطة
print("\n=== ملخص PredictGuard ===")
print(f"عدد الأنشطة المدخلة: {len(activities)}")
print(f"عدد الأنشطة المشبوهة: {suspicious_count}")

if suspicious_count > 0:
    print("🚨 تنبيه: يوجد نشاط مشبوه يحتاج لتدخل الجهات المختصة!")
else:
    print("🎉 لا يوجد نشاط مشبوه. كل شيء آمن.")
