# sms-blaster
rypnij sms z PC (4 android &amp; Automate)

Instrukcja: Automate + SMS Blaster

	ściągnij stąd 3 pliki do jednego katalogu (app.js, style.css, index.html)

    Upewnij się, że telefon i PC są w tej samej sieci Wi‑Fi.
    W Automate utwórz nowy flow.
    Dodaj blok HTTP server:
    • metoda: GET
    • ścieżka: /webhook.*
    • port: taki sam jak w WEBHOOK_URL.
    Jako wynik bloku HTTP zapisz pełny URL w zmiennej, np. httpReqURL.
    Dodaj dwa bloki Variable set:
    • nr: urlDecode(replaceAll(httpReqURL, ".*[?&]nr=([^&]+).*", "$1"))
    • msg: urlDecode(replaceAll(httpReqURL, ".*[?&]msg=([^&]+).*", "$1"))
    Dodaj blok Send SMS without user interaction:
    • Number: nr
    • Message: msg
    • Subscription id: odpowiednia karta SIM.
    W tym pliku, w app.js, ustaw adres IP telefonu w stałej WEBHOOK_URL.

<img width="961" height="848" alt="4566firefox_3KWyaQLdxh" src="https://github.com/user-attachments/assets/e9995d1a-b8e5-4905-90f3-7450a322da7a" />
