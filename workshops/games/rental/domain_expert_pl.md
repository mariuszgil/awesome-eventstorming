# Event Storming Workshop - Wypożyczalnia gier

## Ekspert Domenowy - Wszechwiedzący

Jesteś współzałożycielem sieci wypożyczalni istniejącej od 10 lat. Dotychczas prowadziliście głównie biznes offline w którym wszystkie 30 z Waszych wypożyczalni stacjonarnych umożliwiały wypożyczanie gier planszowych.

W związku ze wzrostem konkurencyjności na rynku, chcecie stworzyć system informatyczny do wspierania Waszego biznesu. Zatrudniliście grupę informatyków, którzy zaproponowali zrobienie czegoś co nazywali warsztatem, aby w jak najszybszy sposób przekazać im wiedzę potrzebną do stworzenia systemu. Wydaje się spoko.

Poza samą implementacją systemu dla sieci wypożyczalni stacjonarnych chcecie wyjść do internetu i umożliwić klientom przegląd dostępnych gier, ich rezerwowanie, zasilanie konta pre-paid. Wraz z procesem cyfryzacji Waszej firmy ostatnim elementem projektu będzie spięcie danych z całej sieci z systemem business intelligence, aby zyskać jeszcze większą przewagę nad konkurencją.

Staraj się pomóc informatykom. Dziel się swoją wiedzą. Jeżeli zadadzą pytanie na które nie znajdziesz odpowiedzi w swoich notatkach - postaraj się odpowiedzieć w jak najlepszy sposób dla Twojego biznesu. Pamiętaj jednak, że jest to workshop i mamy ograniczony czas, więc nie popłyń za daleko w przyszłość. :)

Postaraj się przekonać zespół do tego, aby wytworzyć wspólny język, nazewnictwo pojęć… takie które będzie zrozumiałe dla Twoich współpracowników. Zapisujcie pojęcia na kartkach przy użyciu tego uspójnionego nazewnictwa.

__Nie dawaj nikomu poniższych punktów do przeczytania. Opowiadaj o nich własnymi słowami.__

Poniżej znajdują się informacje, które zebrałeś/aś wraz z koleżankami i kolegami z firmy przygotowując się do warsztatu.

## Biznes

* Chcemy stworzyć oprogramowanie dla punktów stacjonarnych wypożyczalni gier.
* Pamiętajmy że jest to sieć wypożyczalni, a nie jedna wypożyczalnia.
* Każdy z punktów stacjonarnych ma inny zestaw gier na stanie magazynowym.
* Kontrolujemy następujące liczby: ilość gier (na stanie + wypożyczone), stan magazynowy, ilość zarezerwowana, ilość wypożyczonych.
* Wypożyczając grę musimy kontrolować ilości dostępne.
* Aktualnie mamy 30 wypożyczalni w 20 różnych miastach Polski.
* Każda z wypożyczalni ma innego administratora, którym zawsze jest jeden z pracowników lokalnych. 
* Sieć wypożyczalni ma jednego administratora globalnego, który może tworzyć nowe wypożyczalnie w systemie.

## Produkty / Gry

* Wypożyczamy gry planszowe.
* Produkty w systemie są identyfikowane przez numery SKU. Zawierają też nazwy gier.
* Każdy z produktów ma przypisany numer EAN który jest kodem kreskowym na opakowaniu gry. Umożliwia to jego skanowanie przy użyciu czytnika kodów kreskowych.
* Czytnik kodów kreskowych działa na takiej zasadzie jak klawiatura i podłącza się go do portu USB lub PS/2.
* Czasami klienci oddają uszkodzone gry lub ze zgubionymi pionkami / kartami. Jest to spory problem w naszym biznesie. 

## Ceny

* Ceny są przypisane do produktów. 
* Jeden produkt ma tylko jedną cenę w obrębie całej sieci wypożyczalni.
* Czasami mamy potrzebę nadawania rabatów wartościowych i procentowych na początkowe ceny produktów. 
* Płatności przyjmujemy tylko w złotówkach.
* Rozważamy możliwość korzystania z kodów rabatowych, ale nie jest to konieczne.
* Każda gra wypożyczana jest domyślnie na 14 dni.
* Jeżeli klient chce przedłużyć czas wypożyczenia do 30 dni to musi dopłacić 10,00 zł, ale musi podjąć o tym decyzję już w dzień wypożyczania gry i od razu wpłacić pieniądze.
* Przedłużenie czasu na zwrot jest drukowane na paragonie jako osobna pozycja. Nazywa się to “Rozszerzeniem okresu wypożyczenia”.
* Jeżeli klient opóźni oddanie gry, trafia na listę dłużników oraz naliczana jest mu kara:
  * do 5 dni opóźnienia - 20,00 zł,
  * do 20 dni opóźnienia - 100,00 zł,
  * powyżej 20 dni opóźnienia - 300,00 zł.
* Dłużnik nie może wypożyczać kolejnych gier, aż do momentu opłacenia kary i oddania gry.

## Wypożyczalnia stacjonarna

* W sklepie stacjonarnym posiadamy kasę fiskalną, która po podłączeniu jej do komputera umożliwia drukowanie paragonów. Dostawca kasy fiskalnej dostarczył bibliotekę pozwalającą w bardzo łatwy sposób drukować paragony. Możemy ją udostępnić informatykom.
* Każde wypożyczenie kosztuje i może być opłacone:
  * Gotówką,
  * Kartą,
  * Z pieniędzy na koncie prepaid powiązanym z kontem użytkownika w wypożyczalni internetowej,
  * Voucherem prezentowym.

## Wypożyczalnia internetowa

* Klient może się zarejestrować i zalogować.
* Klient może przeglądać gry według kategorii.
* Klient może wejść na stronę konkretnej gry, aby o niej poczytać.
* Klient może zarezerować grę i w ciągu 2 dni odebrać ją w punkcie stacjonarnym.
* Po rezerwacji i wybraniu punktu stacjonarnego gwarantujemy dostawę gry do tego punktu w ciągu 1 godziny (nawet gdy nie ma jej na stanie magazynowym, a jest dostępna w innym punkcie stacjonarnym).
* Jeżeli klient nie odbierze zarezerwowanej gry po 2 dniach - rezerwacja jest anulowana i gra staje się ponownie dostępna dla innych klientów. 
* Rezerwacja jest darmowa, ale musimy mieć jakiś mechanizm zabezpieczający przed dzieciakami rezerwującymi gry tylko po to, aby zepsuć nam biznes.
* Klient może wpłacić pewną pulę pieniędzy na swoje konto w wypożyczalni internetowej (prepaid) i wykorzystywać wpłacone pieniądze do opłacania wypożyczeń.
* Wpłacanie pieniędzy na konto prepaid obsługuje zewnętrzna bramka płatności.
* Nie przewidujemy możliwości wysyłania gier do klientów. Możliwy jest tylko odbiór osobisty. 
* W momencie odbioru zarezerwowanej gry, pobierane są pieniądze z konta pre-paid lub wymagana jest płatność w punkcie stacjonarnym.
* Super gdyby użytkownicy otrzymywali notyfikacje mailowe lub SMSowe.

## Faktury

* Nie dopuszczamy możliwości wystawiania faktur.

## W przyszłości

Skorzystaj z tych punktów jeżeli zespołowi będzie szło wyjątkowo dobrze. Jeżeli będzie szło wolno to nie zaczynaj tematu.

* Chcemy przesyłać dane z systemu do zewnętrznej hurtowni danych, która będzie źródłem danych dla systemu Business Intelligence. Będzie tam analizowana wielkość sprzedaży, statystyki poszczególnych gier, statystyki poszczególnych lokalizacji.
* Rozważamy rozpoczęcie wypożyczania gier komputerowych oraz konsolowych, a także licencji na gry online (tzw. produkty cyfrowe).
* Jeżeli naszemu klientowi spodobała się gra - może ją wykupić.
  * Przed wykupieniem konieczne jest jednak wypożyczenie gry,
  * Wykupienie możliwe jest tylko w punkcie stacjonarnym, a nie jest możliwe w wypożyczalni internetowej.

