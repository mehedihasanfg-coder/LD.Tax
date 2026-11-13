# ভূমি উন্নয়ন করের (আনুমানিক) হিসাব — iPhone Web App

## ফাইল
- `index.html`: অ্যাপ
- `manifest.webmanifest`: Home Screen app configuration
- `sw.js`: offline cache
- `icon-192.png`, `icon-512.png`: app icons

## iPhone-এ ইনস্টল
1. ফাইলগুলো HTTPS-সমর্থিত static hosting-এ প্রকাশ করুন (যেমন আপনার নিজস্ব hosting বা GitHub Pages/Netlify)।
2. iPhone-এর Safari-তে প্রকাশিত `https://...` ঠিকানা খুলুন।
3. Share বোতাম চাপুন।
4. **Add to Home Screen** নির্বাচন করুন।
5. নাম দেখে **Add** চাপুন।

নোট: iOS-এ Home Screen web app ইনস্টল করতে HTTPS hosting দরকার। শুধু ZIP ফাইল বা `file://` থেকে সরাসরি PWA ইনস্টল হয় না। এই প্যাকেজে কোনো সার্ভার বা ব্যবহারকারীর তথ্য সংগ্রহের ব্যবস্থা নেই।


## Updated iPhone build
This build fixes bottom content clipping in iOS Home Screen mode by allowing natural page height and vertical scrolling, and by adding safe-area-aware bottom padding. The service-worker cache is versioned as v2 so the new files replace the old cached build.
After redeploying, close the old Home Screen app fully and reopen it. If it still shows the old version, remove the old Home Screen icon and add the site again from Safari.


## Final display adjustment (v3)
Removed the caption 'আনুমানিক মোট টাকা' completely from the total section, including its separate small-text element. The total amount remains visible in the green total panel.


## Layout spacing update (v4)
The total amount panel now has extra top and bottom spacing, and the reset button is separated from it to prevent overlap on iPhone screens. The service-worker cache is versioned as v4.

## Publish with GitHub Pages
1. Open Settings → Pages in this repository.
2. Under Build and deployment, choose **GitHub Actions** as the source.
3. The included workflow deploys the static app automatically after each push to `main`.
4. After the first successful deployment, open the Pages URL shown in Settings → Pages.
5. On iPhone, open that HTTPS URL in Safari → Share → Add to Home Screen.
