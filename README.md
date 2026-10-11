# 🎣 Phishing URL Detector | كاشف روابط التصيد

**[English](#english) | [العربية](#العربية)**

![Screenshot](screenshot.png)

---

## English

A client-side tool that analyzes the structure of a URL and scores its phishing risk from 0 to 100, explaining every indicator it finds. Nothing is sent anywhere and the link is never opened.

**Live demo:** (https://ghala-it.github.io/phishing-url-detector)

### Features
- Risk score with three levels: likely phishing, suspicious, no clear signs
- URL anatomy view: protocol, subdomain, registered domain, path
- Explanation for every detected indicator
- Brand impersonation check, including Saudi brands (Al Rajhi, STC Pay, Absher, Nafath)

### Indicators
| Indicator | Why it matters |
|---|---|
| Brand lookalike (`paypa1`, `rajhi-bank`) | Imitates a trusted domain |
| Brand name in subdomain or path | The real domain is somewhere else |
| IP address as host | Official sites rarely use one |
| `@` in the URL | Everything before it is ignored by the browser |
| Punycode (`xn--`) | Lookalike characters from other scripts |
| Urgency keywords (`verify`, `otp`, `login`) | Pushes victims to act fast |
| Risky TLD, URL shortener, unusual port, long URL, many subdomains, many hyphens | Common in phishing campaigns |

### How it works
1. Parse the URL into its components
2. Run each indicator check (each returns points and a reason)
3. Sum the points (capped at 100) and map to a verdict
4. Render the score, colored URL parts, and the reasons

### Usage
Open the live demo, or open `index.html` in any browser. Paste a URL and press the analyze button. No installation needed.

### Limitations
This is a rule-based heuristic that looks at the shape of the URL only. A well-built phishing site can pass, and a legitimate site can score points. It is a learning project, not a replacement for tools like Google Safe Browsing.

### Roadmap
- [ ] Train an ML model on PhishTank data and compare it with the rules
- [ ] Domain age check (WHOIS)
- [ ] Reputation check through Google Safe Browsing API
- [ ] Unit tests

---

## العربية

أداة تعمل داخل المتصفح تحلل شكل الرابط وتعطيه درجة خطورة تصيد من 0 إلى 100، مع شرح كل مؤشر تكتشفه. لا يُرسل شيء لأي جهة ولا يُفتح الرابط.

**التجربة المباشرة:** https://ghala-it.github.io/phishing-url-detector

### المميزات
- درجة خطورة بثلاثة مستويات: تصيد محتمل، مشبوه، لا مؤشرات واضحة
- تفكيك الرابط بالألوان: بروتوكول، نطاق فرعي، نطاق أساسي، مسار
- شرح لكل مؤشر مكتشف
- كشف انتحال العلامات التجارية، ومنها السعودية (الراجحي، STC Pay، أبشر، نفاذ)

### طريقة التشغيل
افتحي رابط التجربة المباشرة، أو افتحي ملف `index.html` في أي متصفح، والصقي الرابط واضغطي زر الفحص. لا يحتاج تثبيت.

### الحدود
الأداة تعتمد على قواعد استدلالية تفحص شكل الرابط فقط. موقع تصيد متقن قد يمر، وموقع سليم قد ياخذ نقاط. هي مشروع تعليمي وليست بديلاً عن أدوات مثل Google Safe Browsing.

### خطوات التطوير القادمة
- [ ] تدريب نموذج تعلم آلة على بيانات PhishTank ومقارنته بالقواعد
- [ ] فحص عمر النطاق (WHOIS)
- [ ] فحص السمعة عبر Google Safe Browsing API
- [ ] إضافة اختبارات وحدة

---

Built with HTML, CSS and JavaScript as a cybersecurity learning project.
