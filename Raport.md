# **Bezpieczeństwo Systemów Informatycznych**
## Raport Bezpieczeństwa
* *Data wykonania raportu: 20.01.2022* 
* *Wersja 1.0*

***

Aplikacja  *Vulnerable Web Application*. Strona zostałą przygotowana jako przykład wrażliwej aplikacji, podatnej na różnego typu ataki.

------

![alt text](Front.png)
***
### 1. **Aplikacja** 
>+ **Nazwa:** *Vulnerable Web Application*
>+ **Technologia aplikacji:** *Apache 2.4.18, PHP 5.6.21*
>+ **Back-end:** *MySql 5.0*
>+ **Repozytorium:** *[Link to Repository](https://github.com/OWASP/Vulnerable-Web-Application)*

***
**Opis:**

**Vulnerable-Web-Application** to strona, która jest przygotowana dla osób, które interesują się testami penetracyjnymi i chcą mieć informacje na ten temat lub pracować. Strona jest dość prosta w instalacji i użytkowaniu.

Vulnerable-Web-Application obejmuje Command Execution, File Inclusion, File Upload, SQL oraz XSS. Dla kategorii wymagających bazy danych, tworzy bazę danych pod localhost za pomocą jednego przycisku podczas konfiguracji. W przypadku uszkodzonych lub zmienionych baz danych, można utworzyć bazę danych ponownie.

**Licancja:** Aplikacja jest licencjonowana na zasadach GNU General Public License v3.0.

___

### 2. **Klasyfikacja podatności**

Na liście poniżej przedstawiono skrótowy opis każdej z podatności. Każdy błąd został oznaczony kolorem, zgodnie z legendą:

![alt text](Obraz1.png)

>+ **Niskie Zagrożenie: –** *wykorzystanie podatności ma niewielki bezpośredni wpływ na bezpieczeństwo aplikacji lub wymaga bardzo trudnych warunków do spełnienia (np. fizyczny dostęp do serwera).*

>+ **Średnie zagrożenie  –** *wykorzystanie podatności może zależeć od zewnętrznych czynników (np. wymaga przekonania użytkownika do kliknięcia w łącze) lub może wymagać trudnych do spełnienia warunków. Ponadto wykorzystanie podatności zazwyczaj umożliwia dostęp tylko do ograniczonej ilości danych lub do danych o mniejszym poziomie istotności.*

>+ **Wysokie zagrożenie  –** *wykorzystanie podatności umożliwia przejęcie pełnej kontroli nad serwerem lub urządzeniem sieciowym albo pozwala uzyskać dostęp (w trybie zapisu i/lub odczytu) do danych o dużym poziomie poufności i istotności. Wykorzystanie podatności pozwala także na uzyskanie dostępu do wrażliwych informacji, może wcześniej wymagać spełnienia pewnych warunków (np. posiadania konta użytkownika w wewnętrznym systemie).*


