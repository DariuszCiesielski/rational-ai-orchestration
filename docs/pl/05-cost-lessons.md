# 05 · Lekcje kosztowe: klasy drogich błędów

[🇬🇧 English](../en/05-cost-lessons.md) · [↑ README](../../README.pl.md)

---

To nie są opowieści wojenne. Każda z poniższych lekcji to **syntetyczny kompozyt** — *klasa* błędu zbudowana na podstawie ogólnego kształtu tego, jak rzeczy idą nie tak, a nie zapis konkretnego zdarzenia, osoby czy projektu. Wartość tkwi w wzorcu i regule, która go zapobiega, a nie w tym, czyj tydzień zrujnowała. Bez dat, bez kwot, bez nazwisk — ponieważ lekcja jest taka sama niezależnie od tych czynników, a szczegóły nie są nikomu potrzebne.

Traktuj każdą z nich jako: *oto sposób na zmarnowanie pieniędzy lub jakości oraz reguła, która temu zapobiega.*

---

## Lekcja 1 — Mechanizm kosztujący więcej niż zadanie

**Klasa błędu.** Rutynowe zadanie — takie, które da się wykonać jednym tanim przebiegiem — jest realizowane przy użyciu ciężkiego sprzętu: skomplikowanej orkiestracji wieloagentowej, modelu premium rozproszonego na wiele równoległych wywołań, procesu znacznie większego niż problem. Praca zostaje wykonana, ale kosztem drastycznie niewspółmiernym do jej trudności. Często bodźcem jest słowo — „dokładnie”, „maksymalnie”, „kompleksowo” — interpretowane jako „użyj największego możliwego aparatu”, a nie „bądź ostrożny”.

**Dlaczego to się dzieje.** Większy rozmiar wydaje się bezpieczniejszy i bardziej rzetelny. Skomplikowany mechanizm *wygląda* na rygorystyczny. A koszt jest niewidoczny w momencie wyboru — widzisz aparat, nie fakturę.

**Reguła.** *Dopasuj wagę mechanizmu do wagi zadania.* „Dokładnie” opisuje **jakość wniosku**, a nie **rozmiar aparatu** — możesz być dokładny przy użyciu lekkiego narzędzia. Zanim sięgniesz po orkiestrację lub rozproszoną flotę modeli premium, zapytaj, czy pojedynczy sekwencyjny przebieg na tanim modelu nie da tego samego wyniku. Zazwyczaj tak.

---

## Lekcja 2 — Iterowanie bez punktu odniesienia

**Klasa błędu.** Działający proces jest „ulepszany” przez kilka rund. Każda zmiana wydaje się lokalnie rozsądna. Nikt nie porównuje nowego wyniku ze *starym* wynikiem na tych samych danych wejściowych. Jakość powoli i niewidocznie spada — a ponieważ każdy krok wydawał się postępem, regresja jest odkrywana znacznie później, gdy dobry wersję trudno już przywrócić.

**Dlaczego to się dzieje.** Wewnętrzne metryki („wynik wzrósł”) oderwują się od metryki, która naprawdę ma znaczenie (czy wynik nadal spełnia swoją funkcję). Optymalizujesz proxy i tracisz cel. Bez zamrożonego punktu odniesienia do porównania nie ma sygnału, że cofasz się w miejscu.

**Reguła.** *Ustal punkt odniesienia przed ponownym przetwarzaniem czegokolwiek w skali.* Na małej, stałej próbce porównaj nową wersję z poprzednią — te same dane wejściowe, obok siebie. Jeśli nowa wersja jest istotnie gorsza, zatrzymaj się i zdiagnozuj problem *przed* uruchomieniem pełnej partii. I zachowaj jedną nadrzędną metrykę, która odzwierciedla prawdziwy sukces, a nie wewnętrzne proxy, które może rosnąć, podczas gdy rzeczywistość się pogarsza.

---

## Lekcja 3 — Budowanie na niezweryfikowanym twierdzeniu

**Klasa błędu.** Notatka z przeszłości — wcześniejsza diagnoza, przekazanie zadań, „ustaliliśmy, że X” — jest traktowana jako fakt. Cały łańcuch rozumowania lub kalkulacja kosztów jest na niej budowana. Oryginalne twierdzenie było w momencie pisania *hipotezą*, nigdy nie było ponownie weryfikowane. Okazało się błędne. Wszystko, co na nim zbudowano, dziedziczy błąd, a błąd propaguje się przez wszystkie kolejne wnioski, aż coś w końcu zderzy się z rzeczywistością.

**Dlaczego to się dzieje.** Poprzednie notatki mają fałszywy autorytet — są zapisane, więc wydają się zamknięte. Ponowna weryfikacja wydaje się zbędna. Koszt sprawdzenia jest mały i natychmiastowy; koszt nie sprawdzenia jest duży i odłożony w czasie, więc stopa dyskontowa cię myli.

**Reguła.** *Traktuj twierdzenia z góry łańcucha jako hipotezy, a nie prawdę ostateczną — zwłaszcza własne, stare notatki.* Zanim zbudujesz cokolwiek na pamiętanej diagnozie, poświęć niewielką ilość czasu na jej potwierdzenie wobec obecnej rzeczywistości (przeczytaj rzeczywisty stan, wykonaj faktyczne sprawdzenie). Każda liczba w kalkulacji wymaga pochodzenia: źródła, jawnego założenia lub wyprowadzenia z innych, udokumentowanych liczb. Liczba bez pochodzenia to zgadywanka w garniturze.

---

## Lekcja 4 — Płacenie za komfort

**Klasa błędu.** Model premium jest wybierany nie dlatego, że zadanie go wymaga, ale dlatego, że *czuje się lepiej* — bezpieczniej, poważniej, rzetelniej. Nie wykryto braku konkretnych możliwości tańszego modelu; nawet go nie wypróbowano. Pomnóż to przez miesiąc drobnych decyzji, a rachunek to głównie komfort, nie możliwości.

**Dlaczego to się dzieje.** Wiara, że „mocniejszy = lepszy wynik”, działa nawet wtedy, gdy nie możesz nazwać różnicy. To domyślne ludzkie sięgnięcie po największe dostępne narzędzie i jest całkowicie niewidoczne w ramach pojedynczej decyzji — każda indywidualna eskalacja wydaje się nieszkodliwa.

**Reguła.** *Jeśli nie potrafisz nazwać konkretnej rzeczy, której tańszy model by nie zrobił, płacisz za komfort.* Uczyń opcję tanią taką, która nie wymaga uzasadnienia, a drogą wyjątkiem, który wymaga. Stosuj test pięciu sekund (zob. [reguły eskalacji](./03-escalation-rules.md)) za każdym razem. Komfort jest rzeczywisty, ale nie jest powodem.

---

## Wątek łączący wszystkie cztery

Każda z tych lekcji to wariant tej samej przyczyny źródłowej: **koszt (pieniądza lub jakości), który był niewidoczny w momencie podejmowania decyzji.** Cena mechanizmu, powolny dryf, niezweryfikowane twierdzenie, premia za komfort — żadne z nich nie ogłaszają się, gdy wybierasz. Cała metodologia to zbiór nawyków mających na celu uczynienie tych niewidocznych kosztów *widocznymi w momencie decyzji*: nazwij powód, sprawdź punkt odniesienia, zweryfikuj twierdzenie, dopasuj narzędzie. Dyscyplina nie jest tu cnotą. To po prostu przeniesienie kosztu z powrotem tam, gdzie możesz go zobaczyć, zanim go zapłacisz.

## Gdzie iść dalej

- [Filozofia](./01-philosophy.md) — zasada, którą bronią te lekcje.
- [Przegląd międzymodelowy](./04-cross-model-review.md) — oraz uczciwa uwaga, że przegląd *nie* wychwyciłby większości z tych błędów; to niepowodzenia dyscypliny, a nie luki w rozumowaniu.

---
