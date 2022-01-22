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


<p align="center">
  <img width="600" height="90" src="Obraz1.png">
</p>

>+ **Niskie Zagrożenie: –** *wykorzystanie podatności ma niewielki bezpośredni wpływ na bezpieczeństwo aplikacji lub wymaga bardzo trudnych warunków do spełnienia (np. fizyczny dostęp do serwera).*

>+ **Średnie zagrożenie  –** *wykorzystanie podatności może zależeć od zewnętrznych czynników (np. wymaga przekonania użytkownika do kliknięcia w łącze) lub może wymagać trudnych do spełnienia warunków. Ponadto wykorzystanie podatności zazwyczaj umożliwia dostęp tylko do ograniczonej ilości danych lub do danych o mniejszym poziomie istotności.*

>+ **Wysokie zagrożenie  –** *wykorzystanie podatności umożliwia przejęcie pełnej kontroli nad serwerem lub urządzeniem sieciowym albo pozwala uzyskać dostęp (w trybie zapisu i/lub odczytu) do danych o dużym poziomie poufności i istotności. Wykorzystanie podatności pozwala także na uzyskanie dostępu do wrażliwych informacji, może wcześniej wymagać spełnienia pewnych warunków (np. posiadania konta użytkownika w wewnętrznym systemie).*

___

### 3. **Lista odnalezionych podatności - szczegóły**

Niniejszy raport jest podsumowaniem testów bezpieczeństwa przeprowadzonych w celu wykrycia ewentualnych luk w oprogramowaniu. Przedmiotem  sprawdzenia była aplikacja webowa *Vulnerable Web Application*.

W trakcie audytu szczególny nacisk położono na podatności mające lub mogące mieć negatywny wpływ na poufność, integralność oraz dostępność przetwarzanych danych. Testy bezpieczeństwa przeprowadzono zgodnie z powszechnie przyjętymi metodykami testowania aplikacji webowych, takimi jak: **OWASP TOP10**
#### a. *Podatności XSS (Cross-Site Scripting)*

    Na czym polega istota podatności XSS? Po pierwsze jest to przede wszystkim atak na klienta korzystającego z podatnej webaplikacji (w przeciwieństwie np. do SQL injection, którego głównym celem jest część serwerowa). 
    
    Po drugie, atak polega na wstrzyknięciu do przeglądarki ofiary fragmentu javascript który może być uruchomiony w przeglądarce.

    W efekcie, atakujący ma możliwość wykonania dowolnego kodu skryptowego w przeglądarce 

**Poziom ryzyka:**
<p align="center">
  <img width="200" height="90" src="zs.png">
    </p>

    Liczne wystąpienia, m.in. nazwa użytkownika w historii logowania, nazwy produktów itp. 
    Brak lub dowolne konto w systemie (w zależności od konkretnego wystąpienia).

<p align="center">
  <img width="600" height="100" src="A01.png">
    </p>
<p align="center">
  <img width="600" height="160" src="A02.png">
    </p>
    <p align="center">
  <img width="600" height="120" src="A03.png">
    </p>  
    <p align="center">
  <img width="600" height="140" src="A04.png">
    </p>   
    <p align="center">
  <img width="600" height="140" src="A05.png">
    </p>   
    <p align="center">
  <img width="600" height="160" src="A06.png">
    </p>    
    <p align="center">
  <img width="600" height="100" src="A07.png">
    </p>
    
**Rekomendacja:**
    Filtrowanie wprowadzanych danych oraz sprawdzenie znaków potencjalnie niebezpiecznych. Zmiana znaków zpecjalnych na encje.

#### b. *Podatności Sql Injection*

**Poziom Ryzyka:**

<p align="center">
  <img width="200" height="90" src="wz.png">
    </p>

    W aplikacji zidentyfikowano błędy SQL Injection, pozwalające napastnikom na pełny dostęp do bazy danych danej 
    instancji W konsekwencji wykorzystania tej podatności możliwy jest:

    Widoczna informacja na temat  bazy danych oraz znajdujących się w niej tabel.

<p align="center">
  <img width="320" height="400" src="Table.png">
    </p>
    <p align="center">
  <img width="600" height="120" src="A07_1.png">
    </p>
    <p align="center">
  <img width="600" height="120" src="A07_2.png">
    </p>
    <p align="center">
  <img width="600" height="120" src="A07_3.png">
    </p>    
    <p align="center">
  <img width="600" height="180" src="A07_4.png">
    </p>

    W aplikacji zidentyfikowano błędy SQL Injection, pozwalające napastnikom na pełny dostęp do bazy danych danej instancji YetiForce. W konsekwencji wykorzystania tej podatności możliwy jest: • Dostęp do hashy haseł użytkowników systemu, • Dostęp do danych wszystkich kontrahentów, • Dostęp do treści maili.