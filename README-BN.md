# Meghrong Grocery Android APK (WebView)

এই প্রজেক্ট `https://meghgrocery.netlify.app/` ওয়েবসাইটকে Android WebView অ্যাপ হিসেবে খুলবে।

## GitHub থেকে APK বানানোর নিয়ম

1. GitHub-এ নতুন repository তৈরি করুন, যেমন `meghrong-grocery-apk`।
2. এই ZIP-এর **ভেতরের সব ফাইল** repository-র root-এ upload করুন; ZIP ফাইলটিকে শুধু upload করবেন না।
3. Repository-র `Actions` tab খুলুন এবং GitHub Actions enable করতে বললে enable করুন।
4. বাম পাশ থেকে `Build Meghrong Grocery APK` workflow নির্বাচন করুন।
5. `Run workflow` চাপুন, তারপর সবুজ `Run workflow` বোতামে চাপুন।
6. Build সফল হলে workflow run খুলে নিচের `Artifacts` অংশ থেকে `Meghrong-Grocery-APK` ডাউনলোড করুন।
7. Artifact ZIP extract করে `app-debug.apk` ফোনে ইনস্টল করুন। Android চাইলে “Install unknown apps” অনুমতি দিন।

## কীভাবে কাজ করে

- GitHub Actions-এ JDK 17, Android SDK Platform 35, Build Tools 35.0.0 এবং Gradle 8.7 সেটআপ হয়।
- এই Workflow Gradle Wrapper JAR-এর ওপর নির্ভর করে না; তাই wrapper JAR না থাকার কারণে build ব্যর্থ হওয়ার সমস্যা এড়ানো হয়।
- এটি debug APK, ব্যক্তিগত পরীক্ষা/ইনস্টলেশনের জন্য। Play Store প্রকাশের জন্য release signing দরকার।
- APK অনলাইনে `https://meghgrocery.netlify.app/` লোড করে। ওয়েবসাইট বা ইন্টারনেট বন্ধ থাকলে ওয়েব-নির্ভর ফিচার চলবে না।
- Android app ID: `net.meghrong.grocery`. পরে update APK ইনস্টল করতে চাইলে একই app ID/signing key রাখতে হবে।
