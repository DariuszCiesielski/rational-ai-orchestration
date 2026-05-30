# 03 · Reguły eskalacji: kiedy płatność jest uzasadniona

[🇬🇧 English](../en/03-escalation-rules.md) · [↑ README](../../README.pl.md)

---

Mapa delegacji wskazuje, *gdzie zacząć*. Ten dokument mówi, *kiedy wyjść z taniego domyślnego rozwiązania*. Celem jest krótka, wyraźna lista powodów — na tyle krótka, by „może byłoby lepiej” nie mogło się na niej ukryć.

## Cztery powody (ramy decyzyjne)

Eskaluj do modelu płatnego, gdy **przynajmniej jeden** z poniższych warunków jest spełniony. Jeśli żaden nie zachodzi, pozostań przy modelu lokalnym.

### 1. Bariera możliwości — model lokalny po prostu nie potrafi

Istnieją rzeczy, których darmowe modele lokalne nie potrafią wykonać — punkt:

- **Aktualne badania online** z użyciem bieżących źródeł.
- **Kontekst większy niż pomieści twój model lokalny** — korpus, który po prostu się nie zmieści.

To nie są „eskalacje” w dyscyplinarnym rozumieniu. To inne narzędzie do innego zadania. Płać bez wahania; nie ma tańszej ścieżki, która zadziała.

### 2. Wysokie stawki — decyzje nieodwracalne lub kosztowne w przypadku błędu

Gdy decyzji trudno cofnąć lub naprawa jest kosztowna, druga lub trzecia *niezależna* płatna opinia może być warta swojej ceny jako ubezpieczenie:

- Decyzje architektoniczne dotykające wielu elementów systemu.
- Operacje nieodwracalne (migracje danych, wszystko, co dotyczy środowiska produkcyjnego).
- Umowa lub zobowiązanie, z którego trudno się wycofać.

Test nie brzmi „czy to jest dla mnie ważne emocjonalnie” — brzmi „jaki jest koszt błędu w tym przypadku?”. Jeśli naprawa błędu jest tania, eskalacja to ubezpieczenie, którego nie potrzebujesz.

### 3. Martwy punkt — tanie opcje się nie zgadzają lub obie są niepewne

Gdy dwie niezależne, tanie perspektywy naprawdę się kłócą lub obie wyrażają niskie zaufanie, trzeci, płatny głos może złamać pat. Kluczowe słowo to *naprawdę*: dotyczy to prawdziwego martwego punktu, a nie sytuacji „czułbym się lepiej, gdybym zrobił jeszcze jeden sprawdzian”.

### 4. Krytyczny efekt końcowy — jakość jest produktem

Gdy wyjście *jest* tym, za co klient płaci, a jakość stanowi różnicę — oferta, raport, tekst do klienta w języku, w którym liczy się niuans — dopłata może być uzasadniona wartością efektu końcowego, a nie trudnością zadania.

## Przykładowe progi — **dostosuj do swojego kontekstu**

> ⚠️ Poniższe liczby to **ilustracyjne wartości domyślne do rozpoczęcia rozmowy z samym sobą**, a nie przepisy ani czyjeś „rzeczywiste” wartości operacyjne. Twój sprzęt, twoje stawki i tolerancja ryzyka wyznaczają Twoje rzeczywiste progi. Traktuj je jako *kształt* progu, a następnie zastąp je własnymi.

- **Rozmiar kontekstu:** eskaluj do płatnego modelu z długim kontekstem, gdy wejście przekracza *w przybliżeniu komfortowy limit pracy Twojego dużego modelu lokalnego*. Miejsce tej granicy zależy całkowicie od Twojego sprzętu — wyznacz swoje, a następnie uczynij je regułą.
- **Stawki:** przybliżona zasada początkowa brzmi „jeśli błąd w tym miejscu będzie kosztował więcej niż kilka godzin poprawek, kup drugą opinię”. Ustaw poprzeczkę tam, gdzie ma to sens w kontekście Twojego czasu i ryzyka.
- **Martwy punkt:** eskaluj po *dwóch* niezależnych, tanich recenzjach, które się kłócą — nie po jednej niejednoznacznej odpowiedzi.
- **Wartość efektu końcowego:** eskaluj, gdy wartość wyjścia dla klienta wyraźnie przewyższa marginalny koszt API o dużą różnicę — liczy się stosunek, a nie cena absolutna.

Zapisywanie progów ma na celu uczynienie eskalacji *regułą, którą możesz sprawdzić*, a nie *nastrojem, który możesz zracjonalizować*. Niezależnie od wybranych liczb, dyscyplina polega na ich wcześniejszym ustaleniu.

## Test pięciu sekund (używaj go za każdym razem)

Przed każdą eskalacją zadaj sobie pytanie:

> *„Czy to naprawdę trudne lub strategiczne — czy model płatny jest po prostu teraz wygodniejszy?”*

Jeśli nie potrafisz wskazać konkretnej rzeczy, na której tani model by się pomylił, nie przeszedłeś testu. Zostań przy modelu lokalnym.

## Uwaga na niespodziewane rachunki

Dyscyplina eskalacji ma drugi cel poza oszczędzaniem pieniędzy: **unikanie niespodzianek**. Płatne API mogą naliczać opłaty w sposób, który nie jest oczywisty do momentu wystawienia faktury — użycie w tle, ponawianie prób, tokeny „myślenia” naliczane według stawek wyjściowych, zapomniana pętla. Dwa środki ostrożności:

- **Znaj niespodzianki kosztowe swojego dostawcy**, zanim zaczniesz na nim polegać. Niektórzy naliczają ukrytą pracę (wewnętrzne rozumowanie, ponawianie prób narzędzi) po podwyższonych stawkach. Dowiedz się *którzy* — wcześniej, nie po fakcie.
- **Traktuj każde płatne wywołanie jako świadomy akt.** Cała metodologia zmierza do tego, by użycie płatne było zamierzone i rzadkie — co jest również najlepszą obroną przed rachunkiem, którego się nie spodziewałeś.

## Komunikuj powód: użytkownikowi / sobie samemu

Mały nawyk, który się kumuluje: gdy *naprawdę* eskalujesz, **wymień powód na głos** (w logu, komentarzu lub po prostu do siebie) — „używam modelu płatnego, bo to badanie online” lub „bo ta decyzja jest nieodwracalna”. Wymienienie powodu robi dwie rzeczy: potwierdza, że istnieje rzeczywisty powód, i tworzy zapis, który później możesz zweryfikować. Eskalacji, której nie potrafisz uzasadnić, prawdopodobnie nie powinieneś był podejmować.

## Co dalej?

- [Przegląd międzymodelowy](./04-cross-model-review.md) — jak dokładnie działa „druga i trzecia opinia” i gdzie może zawieść.
- [Lekcje kosztowe](./05-cost-lessons.md) — co się dzieje, gdy ta dyscyplina słabnie.

---
