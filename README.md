# PR
Proiecte de Rețelistică în Python
Acest repository conține o colecție de aplicații Python care demonstrează concepte de rețelistică, inclusiv comunicații client-server, protocolul DNS, interacțiuni HTTP și gestionarea email-urilor. Fiecare proiect este independent și include instrucțiuni detaliate pentru configurare și utilizare.
Cuprins

Chat Simplu Client-Server (TCP)
Chat UDP Simplu
Client DNS
Client HTTP Magazin Online
Client de Email
Client de Fus Orar

Cerințe Generale

Python 3.x instalat pe sistem.
Acces la linia de comandă/terminal.
Conexiune la internet pentru proiectele care necesită acces la servere externe (ex. NTP, DNS, HTTP API).
Biblioteci suplimentare (detaliate pentru fiecare proiect).

Configurare Generală

Clonează repository-ul:git clone <URL_REPOSITORY>
cd <NUME_REPOSITORY>


Instalează dependințele:Fiecare proiect necesită biblioteci specifice. Rulează comenzile pip indicate în secțiunile corespunzătoare.
Verifică firewall-ul: Asigură-te că porturile folosite (ex. 12345) nu sunt blocate de firewall sau antivirus.


Chat Simplu Client-Server (TCP)
Descriere
O aplicație de chat bazată pe protocolul TCP, care permite mai multor clienți să se conecteze la un server și să comunice între ei.
Cerințe

Python 3.x
Biblioteci standard: socket, threading

Structura fișierelor

server.py: Serverul de chat.
client.py: Clientul de chat.

Configurare

Actualizează adresa HOST în server.py și client.py dacă rulezi pe o rețea (implicit: 127.0.0.1).
Portul implicit este 12345.

Utilizare

Pornește serverul:python server.py

Serverul ascultă pe 127.0.0.1:12345.
Pornește clientul (în alt terminal):python client.py

Introdu un nume de utilizator și trimite mesaje.
Pentru a ieși, tastează iesire.

Note

Destinată testării locale. Pentru rețea, folosește IP-ul real al serverului.
Asigură-te că portul 12345 este liber.

Depanare

Eroare de conexiune: Verifică adresa IP/portul și dacă serverul rulează.
Mesaje blocate: Verifică firewall-ul.


Chat UDP Simplu
Descriere
O aplicație de chat bazată pe protocolul UDP, unde clienții trimit mesaje prin intermediul unui server care le retransmite.
Cerințe

Python 3.x
Biblioteci standard: socket

Structura fișierelor

server.py: Serverul UDP.
client.py: Clientul UDP.

Configurare

În client.py, setează server_address cu IP-ul serverului (ex. 192.168.1.100 sau 127.0.0.1).
Portul implicit este 12345.

Utilizare

Pornește serverul:python server.py

Serverul rulează pe 0.0.0.0:12345.
Pornește clientul (poți rula mai mulți clienți):python client.py

Introdu un nume de utilizator și trimite mesaje.
Pentru a ieși, tastează exit.

Note

UDP nu garantează livrarea mesajelor; pierderile sunt posibile.
Serverul trebuie pornit înaintea clienților.

Depanare

Eroare de conexiune: Verifică IP-ul/portul și dacă serverul rulează.
Mesaje pierdute: Verifică stabilitatea rețelei.

Limitări

Fără mecanisme avansate de gestionare a erorilor.
Potrivit pentru rețele locale sau scopuri educaționale.


Client DNS
Descriere
Un client DNS care rezolvă domenii în adrese IP și invers (reverse DNS) folosind biblioteca dnspython.
Cerințe

Python 3.x
Bibliotecă: dnspython (pip install dnspython)

Structura fișierelor

script.py: Scriptul principal.

Configurare

Instalează dnspython:pip install dnspython



Utilizare

Rulează scriptul:python script.py


Comenzi disponibile:
resolve <domain>: Rezolvă un domeniu (ex. resolve google.com).
resolve <ip>: Rezolvă un IP (ex. resolve 8.8.8.8).
use dns <ip>: Setează un server DNS (ex. use dns 8.8.8.8).
exit: Închide aplicația.



Exemple

resolve google.com → Adrese IP pentru google.com: 142.250.190.14
resolve 8.8.8.8 → Domenii asociate cu 8.8.8.8: dns.google
use dns 8.8.8.8 → DNS server setat la: 8.8.8.8

Depanare

Eroare la rezolvare: Verifică conexiunea la internet sau serverul DNS.
Eroare dnspython: Actualizează pip și reinstalează biblioteca.

Limitări

Suportă doar cereri A și PTR.
Depinde de un server DNS funcțional.


Client HTTP Magazin Online
Descriere
O aplicație de consolă care interacționează cu Fake Store API pentru a gestiona categoriile și produsele unui magazin online.
Cerințe

Python 3.6+
Bibliotecă: requests (pip install requests)

Structura fișierelor

main.py: Scriptul principal.

Configurare

Instalează requests:pip install requests



Utilizare

Rulează scriptul:python main.py


Introdu URL-ul API-ului: https://fakestoreapi.com.
Meniu:
Listează categoriile.
Afișează produsele unei categorii.
Creează/actualizează/șterge categorii (simulate).
Creează produse noi.



Note

Operațiunile de creare/actualizare/ștergere a categoriilor sunt simulate.
Verifică conexiunea la internet dacă API-ul nu răspunde.

Depanare

Eroare requests: Verifică instalarea și interpretorul Python.
API nu răspunde: Încearcă un alt API (ex. https://dummyjson.com).


Client de Email
Descriere
Un client de email care folosește IMAP, POP3 și SMTP pentru a lista email-uri, descărca atașamente și trimite email-uri. Configurat pentru Gmail.
Cerințe

Python 3.x
Biblioteci standard: imaplib, poplib, smtplib, email, os, getpass
Cont Gmail cu parolă pentru aplicații.

Structura fișierelor

email_client.py: Scriptul principal.

Configurare

Configurare Gmail:
Activează verificarea în doi pași.
Generează o parolă pentru aplicații (Securitate > Parole pentru aplicații).


Modifică serverele (imap_server, pop3_server, smtp_server) pentru alți furnizori.

Utilizare

Rulează scriptul:python email_client.py


Introdu adresa Gmail și parola pentru aplicații.
Meniu:
1: Listează ultimele 10 email-uri (IMAP).
2: Descarcă atașamente din ultimul email.
3: Trimite email (cu atașament/reply-to opțional).
4: Ieșire.



Note

Atașamentele sunt salvate în folderul attachments.
Funcționalitatea POP3 este comentată (decomentează pentru activare).

Considerații de securitate

Folosește parola pentru aplicații, nu parola principală.
Securizează folderul attachments.

Limitări

Configurat pentru Gmail; necesită ajustări pentru alți furnizori.
POP3 poate șterge email-urile de pe server.


Client de Fus Orar
Descriere
Un script care afișează ora curentă într-un fus orar specificat (format GMT+X/GMT-X) folosind protocolul NTP.
Cerințe

Python 3.x
Biblioteci: pytz, ntplib (pip install pytz ntplib)

Structura fișierelor

timezone_client.py: Scriptul principal.

Configurare

Instalează dependințele:pip install pytz ntplib



Utilizare

Rulează scriptul:python timezone_client.py


Introdu un fus orar (ex. GMT+2, GMT-5) sau exit pentru a închide.
Output exemplu:
GMT+2 → Ora în GMT+2: 2025-05-16 14:05:23
GMT+13 → Format invalid. Folosiți GMT+X sau GMT-X (X între 0 și 11).



Note

Folosește pool.ntp.org pentru sincronizarea orei.
Necesită conexiune la internet.

Depanare

Eroare NTP: Verifică conexiunea la internet.
Format invalid: Asigură-te că respecți GMT+X/GMT-X (X între 0-11).

Limitări

Suportă doar offset-uri ±11 ore.
Nu acceptă fusuri orare după nume (ex. Europe/Bucharest).


Licență
Acest proiect este licențiat sub Licența MIT. Poți modifica și distribui liber.
Contribuții
Contribuțiile sunt binevenite! Deschide un issue sau trimite un pull request pentru erori, funcționalități sau îmbunătățiri.
Depanare Generală

Eroare de dependințe: Actualizează pip (pip install --upgrade pip) și reinstalează bibliotecile.
Porturi blocate: Verifică firewall-ul pentru portul 12345 sau altele specificate.
Conexiune eșuată: Asigură-te că serverele rulează și IP-urile/porturile sunt corecte.

