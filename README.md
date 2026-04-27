Automatyczna analiza phishingu w mailach (.msg/.eml/.txt). Wyciąga IOC, sprawdza reputację w VirusTotal/AbuseIPDB/URLScan/MXToolbox, rozwija skracacze URL, weryfikuje SPF/DKIM/DMARC/ARC oraz
generuje raport Excel z 9 arkuszami. Dla SOC i analityków bezpieczeństwa.

✨ Funkcjonalności

📨 Obsługa formatów — .msg (Outlook), .eml (MIME), .txt (raw headers)
🔍 Wielowarstwowa analiza IOC — IP, domeny, URLe, adresy e-mail, nagłówki uwierzytelniające
🌐 Integracja z 5 API reputacyjnymi — VirusTotal, AbuseIPDB, URLScan.io, MXToolbox, ip-api.com
🔓 Rozwijanie skracaczy URL — automatyczne podążanie za bit.ly, tinyurl, t.co i 30+ innymi
📦 Ekstrakcja URLi z body — plain text, HTML, RTF, Base64, Quoted-Printable, TNEF (winmail.dat)
🛡️ Analiza SPF/DKIM/DMARC/ARC — pełna weryfikacja łańcucha uwierzytelnienia
📊 Raport Excel — 9 arkuszy z dashboardem, wykresami, cheat sheetem analityka
🎯 Detekcja phishingu — typosquatting (PKO, mBank, Microsoft, Allegro...), spoofing nazwy nadawcy, niezgodność From/Reply-To
📅 WHOIS — wiek domeny (świeże = podejrzane)

🔧 Wymagania

Python 3.13+ (python.org — uwaga, NIE wersja ze Sklepu Microsoft)
Windows 10/11 (testowane)
Klucze API (wszystkie mają darmowe plany):

VirusTotal
AbuseIPDB
URLScan.io
MXToolbox (opcjonalne)

🔐 Bezpieczeństwo

⚠️ Uruchamiać tylko na izolowanej VM
Skrypt podąża za przekierowaniami URL (w tym za skracaczami) bez ograniczeń. Złośliwe domeny mogą:

Próbować exploitować podatności w bibliotekach Pythona
Logować adresy IP analityków
Serwować różne odpowiedzi w zależności od User-Agent
Zawsze uruchamiaj na sandbox VM ze snapshotem.

Klucze API

Nie są zapisywane na dysku — wpisywane przy każdym uruchomieniu
W trakcie działania są w pamięci procesu (standardowo dla każdej aplikacji używającej API)
Po zakończeniu programu — znikają

Co zawiera raport .xlsx
Tylko dane analityczne — nazwy domen, IPs, wyniki analizy. Brak:

Pełnej treści maila
Załączników
Wykonywalnego kodu
Makr Excel

Raport jest bezpieczny do wynoszenia z VM.
Czego NIE wynosić z VM

Oryginalnych plików .msg / .eml (mogą zawierać złośliwe załączniki)
Pobranego content z linków (jeśli wykonywałeś manualne sprawdzenie)

⚠️ Disclaimer
Narzędzie służy do defensywnej analizy bezpieczeństwa wiadomości email otrzymanych przez analityka SOC lub użytkownika końcowego, pamiętaj jest to tylko urządzenie które ma pomóc w analizie a nie w pełni ją zastąpić!!!
Nie używaj do nielegalnych aktywności, naruszania prywatności osób trzecich ani jako narzędzia ofensywnego.
Autor nie ponosi odpowiedzialności za szkody wynikające z niewłaściwego użycia narzędzia ani za fałszywe pozytywne/negatywne wyniki API zewnętrznych dostawców.
Narzędzie jest stale rozwijane, w razie potrzeby wprowadzenia funkcjonalności prośba o wiadomość na maila: nightstalker19606@gmail.com
